
#### Concurrency vs Parallelism

<img src="https://user-images.githubusercontent.com/63919345/215276604-8e8451b4-9f9f-4663-85bc-f8b8239ee632.png" height=300 alt="concurrency-vs-parallelism"/>
<img src="https://user-images.githubusercontent.com/63919345/215277364-1d2be4ba-ed25-4065-bfbe-2a842a425c83.png" height=300 alt="hardware-mapping"/>

|Concurrency  | Parallelism |
|---          |---          |
|may or may not be executed on different hardware | always have to be executed on different hardware (different cpu or core)|
|only one task executed at a time | tasks are executed in parallel |
| supported by Go | not supported by Go|

#### Process, OS, Threads

<img src="https://user-images.githubusercontent.com/63919345/215277940-9b99bff2-0a7e-445d-b731-0ef36f270637.png" height=300 />
<img src="https://user-images.githubusercontent.com/63919345/215278726-5b7172df-556e-43ce-8c8b-3b034f66af65.png" height=300 />
<img src="https://user-images.githubusercontent.com/63919345/215278887-f475061a-c311-40c4-aeb5-f3dfa89ce922.png" height=300 />
- Threads have the advantage of sharing some context over processes which makes switching between executing threads easier.   
- Threads can be called lightweight processes.  

#### Goroutines

Process -> Main Thread -> Multiple Goroutines. 

- Goroutines are run concurrently, but you can modify settings to allow multiple logical processors which can lead to parallelism.

<img src="https://user-images.githubusercontent.com/63919345/215286752-05346303-67ff-410d-8291-39e91865e25b.png"  height=300 />
<img src="https://user-images.githubusercontent.com/63919345/215286822-53abf8b4-dcc6-418c-8b7e-79c4938edcbc.png" height=300 />
