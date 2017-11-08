# IBM Integration BUS
###### IBM Integration Bus provides connectivity across enterprise systems, applications, and data

## IBM Integration Bus themes
1. Simple and productive
2. Universal and independent
3. Industry specific and relevant
4. Dynamic and intelligent
5. High performing and scalable
6. Transform and route data from anywhere, to anywhere
7. Patterns provide reusable solutions
8. Operational managment and performance

## IBM Integration Bus main components
1. Integration node
   - The runtime engine of IBM Integration bus

## IBM Integration Bus runtime components
1. Integration node
   - Routes, transforms, and enriches in-flight messages as determined by message
flows and message models.
   - Can be many integration nodes, each running on separate systems to provide
protection against failure or separate the work.
2. Integration server
   - Named grouping of message flows that are assigned to an integration node.
   - Each integration server is a separate operating system process, which provides
isolated runtime environments for a set of deployed message flow applications.
3. Message flow applications
   - Describe the application connectivity logic, which defines the exact path that the
data takes in the integration node, and the processing that is applied to it by the
message processing nodes in that flow.
   - Reference message models that describe the data.

## IBM Integration Bus operation modes
   Operation modes typically restrict the number of message flow nodes that are available, and
integration server capacity, but many features are available across all modes of operation. This
figure summarizes four of the IBM Integration Bus operation modes: Express, Scale, Standard, and
Advanced. IBM Integration Bus is also available in Developer mode and Adapter mode.

   1. Express
   2. Scale
   3. Standard
   4. Advanced

## IBM Integration Bus processes messages in two ways
1. Message routing
   Messages can be routed from sender to recipient based on the content of the message.
2. Message transformation
   Messages can be transformed before being delivered:
   - They can be transformed from one format to another, perhaps to accommodate the different requirements of the sender and the recipient.
   - They can be transformed by modifying, combining, adding, or removing data fields, perhaps involving the use of information stored in a database. Information can be mapped between messages and databases. More complex manipulation of message data can be achieved by writing code, for example in Extended SQL (ESQL) or Java™, within configurable nodes.
