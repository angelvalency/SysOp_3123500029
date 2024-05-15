<div align="center">
  <h1 style="font-weight: bold"> LAPORAN PRAKTIKUM XI SISTEM OPERASI<br>Producer-Consumer Problem</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    Firsty Angelica Valency (3123500029)<br>
  </p>
  <h3 style="text-align: center;line-height: 1.5">Program Studi Teknik Informatika<br>Departemen Teknik Informatika Dan Komputer<br>Politeknik Elektronika Negeri Surabaya<br>2023/2024</h3>
  <hr>
</div>


# Daftar Isi
- [Tugas Pendahuluan](#Tugas_Pendahuluan)
- [Kesimpulan](#Kesimpulan)

# Tugas Pendahuluan

1. Producer consumer problem menggunakan semaphore sebagai solusi


- Source Code

            #include<stdio.h>
            #include<stdlib.h>
            
            int mutex=1,full=0,empty=3,x=0;
            
            int main()
            {
                int n;
                void producer();
                void consumer();
                int wait(int);
                int signal(int);
                printf("\n1.Producer\n2.Consumer\n3.Exit");
                while(1)
                {
                    printf("\nEnter your choice:");
                    scanf("%d",&n);
                    switch(n)
                    {
                        case 1:	if((mutex==1)&&(empty!=0))
                                    producer();
                                else
                                    printf("Buffer is full!!");
                                break;
                        case 2:	if((mutex==1)&&(full!=0))
                                    consumer();
                                else
                                    printf("Buffer is empty!!");
                                break;
                        case 3:
                                exit(0);
                                break;
                    }
                }
                
                return 0;
            }
            
            int wait(int s)
            {
                return (--s);
            }
            
            int signal(int s)
            {
                return(++s);
            }
            
            void producer()
            {
                mutex=wait(mutex);
                full=signal(full);
                empty=wait(empty);
                x++;
                printf("\nProducer produces the item %d",x);
                mutex=signal(mutex);
            }
            
            void consumer()
            {
                mutex=wait(mutex);
                full=wait(full);
                empty=signal(empty);
                printf("\nConsumer consumes item %d",x);
                x--;
                mutex=signal(mutex);
            }


            /*

            Producer consumer problem is also known as bounded buffer problem. In this problem we have two processes, producer and consumer, who share a fixed size buffer. Producer work is to produce data or items and put in buffer. Consumer work is to remove data from buffer and consume it. We have to make sure that producer do not produce data when buffer is full and consumer do not remove data when buffer is empty.

            The producer should go to sleep when buffer is full. Next time when consumer removes data it notifies the producer and producer starts producing data again. The consumer should go to sleep when buffer is empty. Next time when producer add data it notifies the consumer and consumer starts consuming data. This solution can be achieved using semaphores.
            */
        
- Output 

    ![App Screenshoot](assets/output_simaphore.png)


- Analisis
      
    Dalam masalah ini, ada dua proses, yaitu produsen (producer) dan konsumen (consumer), yang berbagi sebuah buffer dengan ukuran tetap. Tugas produsen adalah menghasilkan data atau item dan menempatkannya di dalam buffer. Sedangkan tugas konsumen adalah mengambil data dari buffer dan mengonsumsinya. Simaphore menggunakan variabel mutex yang digunakan untuk mengontrol akses ke bagian kritis. Nilai mutex 1 menunjukkan bahwa bagian kritis dapat diakses. User dapat memilih proses produsen (akan menampilkan buffer full jika datanya penuh didalam buffer), dan konsumer (menampilkan buffer empty jika datanya diambil semua sehingga buffer kosong).



2. Producer consumer problem menggunakan wake-sleep sebagai solusi

- Source code

        
            #include <iostream>
            #include <cstdlib>
            #include <pthread.h>
            using namespace std;

            // function prototypes
            void* Produce(void* arg);
            void* Consume(void* arg);

            // global variables
            // the mutex and the condition variable
            pthread_mutex_t mutex;
            pthread_cond_t cond;

            // the condition flag
            bool condition = false;

            // the item produced
            int count = 0;

            // how much to produce
            const int NUM_TO_PRODUCE = 10;

            int main()
            {
                // declare variables
                pthread_t producerThread;
                pthread_t consumerThread;

                // initialize the mutex and the condition variable
                pthread_mutex_init(&mutex, NULL);
                pthread_cond_init(&cond, NULL);
                
                cerr<<" The Parent is creating the producer and consumer threads.";

                // create a producer thread
                if(pthread_create(&producerThread, NULL, Produce, NULL) < 0)
                {
                    cerr<<"pthread_create";
                    exit(1);
                }

                // create a consumer thread
                if(pthread_create(&consumerThread, NULL, Consume, NULL) < 0)
                {
                    cerr<<"pthread_create";
                    exit(1);
                }

                // wait for the threads to complete 
                // similar to the wait() system call for fork() processes
                if(pthread_join(producerThread, NULL) < 0)
                {
                    cerr<<"pthread_join";
                    exit(1);
                }

                if(pthread_join(consumerThread, NULL) < 0)
                {
                    cerr<<"pthread_join";
                    exit(1);
                }
                
                cerr<<"Both threads have completed and have terminated!"
                    <<"The Parent is now exiting...n";    

                return 0;
            }// end of main

            /**
            * The producer thread function
            * @param arg - pointer to the thread local data - unused
            */
            void* Produce(void* arg)
            {
                // produce things until the loop condition is met
                while(count < NUM_TO_PRODUCE)
                {
                    // lock the mutex to protect the condition variable
                    if(pthread_mutex_lock(&mutex) < 0)
                    {
                        cerr<<"pthread_mutex_lock";
                        exit(1);
                    }
                    
                    // we have produced something that has not been
                    // consumed yet, so we sleep (wait) until the consumer 
                    // wakes us up.
                    while(condition)
                    {
                        // sleep (wait) on a condition variable until the
                        // the consumer wakes the producer up.
                        if(pthread_cond_wait(&cond, &mutex) < 0)
                        {
                            cerr<<"pthread_cond_wait";
                            exit(1);
                        }
                    }

                    // produce an item
                    cerr<<"Produced: "<<++count<<endl;
                    
                    // we have produced something
                    condition = true;
                    
                    // wake up the sleeping consumer
                    if(pthread_cond_signal(&cond) < 0)
                    {
                        cerr<<"pthread_cond_signal";
                        exit(1);
                    }
                    
                    // release the mutex lock
                    if(pthread_mutex_unlock(&mutex) < 0)
                    {
                        cerr<<"pthread_mutex_unlock";
                        exit(1);
                    }
                }
                return 0;
            }// end of Produce

            /**
            * The consumer function
            * @param arg - pointer to the thread local data - unused
            */
            void* Consume(void* arg)
            {
                // consume things until the loop condition is met
                while(count < NUM_TO_PRODUCE)
                {	
                    // lock the mutex to protect the condition variable
                    if(pthread_mutex_lock(&mutex) < 0)
                    {
                        cerr<<"pthread_mutex_lock";
                        exit(1);
                    }
                    
                    // if there is nothing to consume, then sleep
                    while(!condition)
                    {			
                        // sleep (wait) on a condition variable until the
                        // producer wakes the consumer up.
                        if(pthread_cond_wait(&cond, &mutex) < 0)
                        {
                            cerr<<"pthread_cond_wait";
                            exit(1);
                        }
                    }

                    cerr<<"Consumed: "<<count<<endl<<endl;
                    
                    // consume the item
                    condition = false;
                        
                    // wake up the sleeping producer
                    if(pthread_cond_signal(&cond) < 0)
                    {
                        cerr<<"pthread_cond_signal";
                        exit(1);
                    }
                    
                    // unlock the mutex
                    if(pthread_mutex_unlock(&mutex) < 0)
                    {
                        cerr<<"pthread_mutex_unlock";
                        exit(1);
                    }
                }
                return 0;
            }
            // http://programmingnotes.org/


- Output

    ![App Screenshoot](assets/output-wake-sleep.png)

- Analisis

     Program ini terdapat 2 fungsi thread yaitu produce dan consume. Mutex diinisialisasi sebagai variabel global untuk sinkronisasi antar thread. Jika item telah diproduksi, thread produsen akan menunggu (pthread_cond_wait) hingga thread konsumen mengonsumsi item tersebut.Setelah thread konsumen mengonsumsi item, thread produsen akan memberi tahu thread konsumen (pthread_cond_signal) bahwa produksi telah dilakukan. Kemudian, Jika tidak ada item yang tersedia untuk dikonsumsi, thread konsumen akan menunggu (pthread_cond_wait) hingga ada item yang diproduksi oleh thread produsen. Setelah mengonsumsi item, thread konsumen memberi tahu thread produsen (pthread_cond_signal) bahwa item telah dikonsumsi.



# Kesimpulan

Producen-consumen problem dapat diatasi dengan menggunakan semaphore dan weak sleep. Kita dapat menggunakan semaphore untuk mengatur akses ke buffer yang digunakan produsen dan konsumen, sementara weak-sleep digunakan untuk menunda proses produsen saat buffer penuh dan menunda proses konsumen saat buffer kosong.
