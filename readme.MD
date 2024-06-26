### 1. what is amqp?
Advanced Message Queuing Protocol is a protocol used for sending messages between systems reliably and securely, ensuring that data is delivered even if some parts of the system fail.

### 2. what it means? guest:guest@localhost:5672 , what is the first quest, and what is the second guest, and what is localhost:5672 is for? 
- guest (1st) : username
- guest (2nd) : password
- localhost : hostname
- 5672 : port

## Screenshots
### Slow subscriber simulation
![Slow subscriber simulation](assets/image1.png)
It shows a total of about 21 queues because I ran the `cargo run` command 5 times. The delay comes from the line `thread::sleep(ten_millis);` in the subscriber program, which makes it pause for 10 milliseconds. This simulates a slow subscriber, causing the delay.

### Running three subscriber
![Running three subscriber](assets/image2.png)
The chart shows that the queue count went to 13 when I ran 3 subscribers consecutively. This decrease is due to the subscriber implementing multithreading to handle multiple messages sent and received simultaneously from the publisher. Multithreading allows the messages to be processed in parallel across the three subscribers, enhancing the overall performance within that timeframe. 