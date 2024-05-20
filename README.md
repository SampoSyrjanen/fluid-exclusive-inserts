# Introduction

This is a test program that implements a scenario in which multiple Fluid
clients update a shared sequence simultaneously in a way that each client gets
update events to the sequence in the same order. This is achieved by assigning
one of the clients the task of inserting new elements into the sequence. The
other clients do not directly insert into the sequence but instead communicate
the desire to insert through another DDS. Task assignment is implemented using
the task-manager DDS from the FluidFramework repository.

NOTE: due to some package incompatibilities, the implementation of the
TaskManager DDS has been copied into this repository

# Running the test

Install dependencies using
```
npm ci
```

Compile and bundle test with
```
npm run build
```

Start the local fluid service using
```
npm run start:server
```

To run the test
```
node bundle-node.js
```

To run the test without using exclusive inserts
```
node bundle-node.js no
```
