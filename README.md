# Consumer-Producer-Factory-Organization-Model
The objective for this project was to develop an algorithm for the model organization which has multiple clients and have more than one producer at a time, where the producer is continuously producing some data into a queue on different execution cycles and the consumer must accept data, without the possibility of any deadlocks.

![Welcome to Penultimate (page 17) (1)](https://user-images.githubusercontent.com/77020328/116322590-58148f80-a78a-11eb-89a0-6567e95064f2.png)


Producer Class
In the producer class I had firstly declared my queue with a maximum size of n. 

Then I created the override run method for my producer third and defined and infinite while loop inside which will continuously call the produced method which will in turn continuously produce some data as long as the thread is active.

The way this method works is first of all we check whether or Q is full or not if the key is full then we put out a message saying that queue limit has reached and we are waiting for the consumer to consume and we simply call the weight method which will suspend our  thread as long as the Queue is not empty.

In case accused not full that is accused empty then I simply generate and added the local data and time into our message you by converting it into a string.

Once we are done adding the data to the queue then we call the notify method to notify consumer thread the producer has produced some data into the queue and is ready to be consumed

Instead of defining the consume method in the consumer class, I actually declared it in the producer class so that we can have synchronization across our threads

In this cconsumer method first of all you call the notify method to notify that the consumer is going to consume the data from the Queue by calling the consume method from the producer class.
The way we consume data  is first of all we check whether the message queue is empty or not and if the queue is empty then we simply call the wait method till the queue is full again, and if the queue is full then we simply take the data from the 0th position in the Quue and send it back to the consumer class and once a consumer classes has consumed a specific data then we simply remove the data from the queue

Consumer Class
Coming to the consumer class we first created a producer object so that we can access the consume method which is in our producer class and initialize a generic constructor for the consumer class then similar to the producer class we defined an override and method for our consumer thread and inside it I defined and infinite loop which will use to continuously call the consume method to consume the data once the consumer has retrieve the data we simply print the data that has been consumed on to our output terminal along with the name of the consumer who has consumed it

MAIN class
iN main class I declared and producer object and set a name for the producer thread. Similarly, I  initialized a couple of consumer objects and used the main class to start all of our threads synchronously
