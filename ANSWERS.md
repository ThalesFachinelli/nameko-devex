### Question 1: Why is performance degrading as the test runs longer ?

The longer the tests run the more number requests are sent at a time. One of the biggest
problems in the original implementation is that all the functions are synchronous which makes performance degrade the 
more requests are received specially on functions that need more processing to return results as the list orders 
function for an example.

### Question 2: How do you fix it ?

 The best way to fix this problem is to make the functions async. Just changing the function that take the longest time
to run (list orders) already boost up throughput considerably but keep in mind that changing sync to async makes
 the system more prone to errors during performance tests.
