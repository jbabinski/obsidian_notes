##### [PubSub docs](https://cloud.google.com/python/docs/reference/pubsub/latest)
- publisher/subscriber
- publish message to subscribers
![[Pasted image 20230307112624.png]]
![[Pasted image 20230307112634.png]]
![[Pasted image 20230307112737.png]]

1. Pub/Sub ingests data from various sources
2. Data Flow & BigQuery are subscribed to events
3. Data can be visualized or processed in BigQuery or VertexAI

Topic in Pub/Sub:
- topic connects publishers and subscribers
- subscribers and publishers are decoupled
- there can be 0/1/more subscribers and publishers

![[Pasted image 20230307113352.png]]

##### Processing Streaming Data
![[Pasted image 20231025072712.png]]
- keeps messages for 7 days
- Google uses Pub/Sub to scan the whole www ~3 times a day
![[Pasted image 20231025073026.png]]
Example:
![[Pasted image 20231025073143.png]]
![[Pasted image 20231025073155.png]]
- multiple subscribers:
![[Pasted image 20231025073221.png]]
https://medium.com/@nileshxbhosale/why-decoupling-is-important-from-a-data-engineering-perspective-5b12a941a8a
- Pull subscription
![[Pasted image 20231025073346.png]]
![[Pasted image 20231025073431.png]]
Message filter:
![[Pasted image 20231025073522.png]]

##### Push versus Pull
![[Pasted image 20231025074727.png]]
- left - one publisher, one subscriber
- mid - fan-in/low-balancing. Multi publishers, multi subscribers to one topic
- right - fan-out. One publisher, many subscribers of the same messages

![[Pasted image 20231025075138.png]]
- ACK/acknowledge step to make sure that message went through
![[Pasted image 20231025075231.png]]
![[Pasted image 20231025075517.png]]
- can replay messages and send it to newly created subscribers
![[Pasted image 20231025075616.png]]

##### Publishing with Pub/Sub code
![[Pasted image 20231025080021.png]]
- **b** before string to send bytes - PubSub can send other types of messages (i.e. images)
- 10 MB limit
- can add attributes, like author
![[Pasted image 20231025080206.png]]
![[Pasted image 20231025080340.png]]
- can set # of messages to be received, deadline, sleep time etc.
![[Pasted image 20231025080519.png]]
- you can set the batch settings 
![[Pasted image 20231025080647.png]]
![[Pasted image 20231025080821.png]]
- data split in chunks to be processed by subscribers
![[Pasted image 20231025081048.png]]
- dead-letter sinks and logging recommended to catch problems with PubSub processing
![[Pasted image 20231025081243.png]]
![[Pasted image 20231025081259.png]]
![[Pasted image 20231025081330.png]]