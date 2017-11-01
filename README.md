[![Build Status](http://jenkins.snake.cygni.se/buildStatus/icon?job=snake%20client%20java)](http://jenkins.snake.cygni.se/job/snake%20client%20java/)

This a Snake Client written in Java 8.

## Requirements

* Java JDK >= 8
* Gradle
* Snake Server (local or remote)

## Installation

A. Clone the repository: `git clone https://github.com/cygni/snakebot-client-java.git`.

B. Open: `<repo>/`

C. Execute: `./gradlew build`

## Usage

To clean and build:
```
> ./gradlew clean build
```

To run your client:
```
> ./gradlew run
```

## Implementation

There is only one class in this project, have a look at SimpleSnakePlayer.java. The main method to start in looks like this:

```java
@Override
public void onMapUpdate(MapUpdateEvent mapUpdateEvent) {
    ansiPrinter.printMap(mapUpdateEvent);

    // Choose action here!
    registerMove(mapUpdateEvent.getGameTick(), SnakeDirection.DOWN);
}
```

For every MapUpdateEvent received your are expected to reply with a SnakeDirection (UP, DOWN, LEFT or RIGHT). 
