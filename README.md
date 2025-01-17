# IBM Integration BUS
###### IBM Integration Bus provides connectivity across enterprise systems, applications, and data

# Table of contents

1. [Introduction to IBM Integration Bus](#introduccion-to-iib)
2. [Application development fundametals](#application-development-fundamentals)
3. Creating message flow applications
4. [Connecting to IBM MQ](#connecting-to-ibm-mq)
5. Controlling the flow applications
6. MOdeling the data
7. Processing file data
8. Using problem determination tools and help resources
9. Mapping messages with the Graphical Data Mapping editor
10. Referencing a database in a message flow application
11. Using Compute nodes to transform messages
12. Procesing JMS, HTTP, and web service messages
13. Preparing for production

# Introduccion to IIB

## IBM Integration Bus themes
1. Simple and productive
2. Universal and independent
3. Industry specific and relevant
4. Dynamic and intelligent
5. High performing and scalable
6. Transform and route data from anywhere, to anywhere
7. Patterns provide reusable solutions
8. Operational managment and performance

## IBM Integration Bus features
1. Transform and route data from anywhere to anywhere
2. Patterns provide reusable solutions that encapsulate a tested approach to solving a common architecture, desing, or deployment task
3. Operational managment and performance

## IBM Integration Bus main components
1. Integration node
   - The runtime engine of IBM Integration bus
2. Message flows
   - Provides isolation and scalability
3. Application
   - Container for all the resources that are  required to create a solution

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

# Application development fundamentals

## Main components
   1. Integration node
      Routes, transform, and enriches messages as determined bye message flows and message models.
   2. Integration server
      Named gruping of message flows.
   3. Message flow
      Sequence of operations
   4. Message flow nodes
      Define operations
   5. Message models
      Define structure and properties of the data

## Basic IBM Integration Bus commands

   1. *mqsilist*
       List the IBM Integration Bus components on the system
   2. *mqsistart*
       Start components
   3. *mqsistop*
       Stop components

# Connecting to IBM MQ
 
## IBM  MQ functional overview
   - Common application programing interface
   - Assuraded message delivery
   - Time-independent processing
   - Application parallelism
   - Faster application development

## Messages
   - Contain the application data or payload
   - Are placed o queues
   - Contain IBM MQ message descriptor (MQMD) with control information
   - Can contain optional message properties that the applications creates

## Queues
   - A queue is a place to store message until  the can be processed

## IBM MQ  connectivity options with  IBM Intragration Bus
   - Message flow applications can access existing IBM MQ networks to get o input a messages
   - Globally coordinated transaction control requires  that MQInput and the MQOuput  nose use the same local queue manager
   - The MQ Connection properties are available on the following MQ nodes:
     - MQInput
     - MQOutput 
     - MQGet 
     - MQReply

# Modeling the data

## Message modeling
   - Most messages require a model at run time to parse the message bit stream from the physical data and serialize to create the physical bit stream from model.
   - Modeling accelerates the development of transformations at design time in the IBM Integration Toolkit
   - Validationn can be used for checking message correctness when parsing.

## Message model object properties
   - Logical model is a format-independent description, similar to default values.
   - Physical model
   - Documentation does not affect processing

## Parser types
   - Programmatic parsers
   - Descriptive parsers
   - IBM Integration Bus uses both approaches

## Model definition files
   - Describe the logical structure of the message
   - Describe the physical formats of the message bit stream during transmission.
   - Can be imported from WSDL, an XML schema, DTD, COBOL ord C.
   - Contains a message model with message, elements, types, and so on
   - Based on XML schema standards

## Data Format Description Language (DFDL)
   - An open standart from Open Grid Forum (OGF)
   - Uses XML technology and concepts
   - Describes any data format
   - Support round-trippig

## When should you use DFDL?
   - Use DFDL to model:
     - Binary data
     - Text data with delimiters such as csv
     - Text industry standars
     - Binary industry sntandars
   - Do not use DFDL to model:
     - XML data that can use XML parsers and have a XML schema
     - JSON that can use JSON parsers
   -  Do not use DFDL expressions to implement complex validation rules

# Controllig the flow of messages

## Logical message model
   - A consistent, convenient way to represent message content inside IBM Integration Bus
   - Removes and isolates the physical details of message
   - Organizaed as message assembly that contains four trees:
     - Message tree
     - Enviroment tree
     - Local enviroment tree
     - Exception tree
   - Element values are stored in Unicode to facilitate code conversion
   - Elements in the tree are addressed by using XPath or the dotted name notation

## Message routing nodes
   - Filter
   - Route
   - Label
   - FlowOrder  

# Processing file data

## Files processing node
   1. Generic
      - FileInput
      - FileRead
      - FileOutput
   2. IBM Sterling Connect: Direct
      - CDInput
      - CDOutput
   3. IBM MQ File Transfer Edition
      -FTEIput 
      -FTEOuput

# Processing JMS, HTTP and Web service messages

## Java Message Service (JMS)
   JMS provides a standard API for Java applications to use for enterprise messaging. Java standards are controlled through the Java Community Process. It was developed with input from many messaging providers, including IBM.

## JMS architecture
   - JMS client
   - Messaging provider
   - Message
   - Administered objects(Connection Factory and Destination)

   Java Naming and Directory Interface (JNDI) is a standard Java extension that provides a uniform API for accessing various directory and naming services.

## IBM Integration Bus support for JMS

   IBM Integration Bus support the JMS version 1.1 and 2.0 standard. It uses the IBM Integration Bus JMS Transport Service to connect to JMS messaging providers.

## JMS nodes

   The JMS nodes can be used in applications in which messages are produced and used from various JMS destinations. In sending and receiving messages, the JMS nodes behave like JMS clients. 
