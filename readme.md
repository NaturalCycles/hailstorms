




# Hailstorms

Hailstorms is a distributed load test framework based on locust.io.
The benefits of Hailstorm is that you can load test on an arbitrary number of machines and the only thing you need besides the Hailstorms framework is bash and Docker

```

             _
         ___( ).
      . (        ).
     (  Hailstorm  )
      (___________)
      / / / · / /
     / • / / · /
    ᠂ / ・ · / ᛫

```




## Setup

Before you can perform any load tests you need to initialize your working directory.
The rest of this readme will assume you have choosen our selection of folders:

* __hailstorm__ - Here the initialization will create some scripts for your convenience.
* __scripts__ - Here is where you place your load test scripts.

You can select any other names for your folders but these are the once we are going to refer to later.

##### Start the initialization

Initialization is built into the docker image so we need to call that.

Make sure you are in the directory where you want the two folders above.

    $ mkdir hailstorm
    $ docker run --rm -it -v ${PWD}/hailstorm:/opt/hailstorms/helpscripts romram/hailstorms init

Follow the instructions written in the terminal and execute:

    $ hailstorm/init

_Beside the two folders mentioned an additional folder called `generated` has been created.
Files that are generated by the script are stored here._




## Normal flow

You will need a python script defining how you want to load test and a number of ip addresses to your load test machines should you not want to load test from your local machine.

    hailstorm/start start --script scripts/demo.py --profile local

