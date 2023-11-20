# OpenAI error report ticket #769 

This is an error demonstration that applies for OpenAI python sdk version 1.3.3. 

The error is the following:
We have two threads A and B. We create the OpenAI object on thread A and call the OpenAI object's function
simultaneously on A and B threads. If the B thread starts before thread A, it will be stuck in the HTTP core module in
the connection file pool lock in thread B. But if thread A starts first then thread B also finish without stucking.

The solution is to create the Async OpenAI object on both threads A and B.