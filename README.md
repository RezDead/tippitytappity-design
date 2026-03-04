# tippitytappity-design

tippitytappity is a program to practice typing


## Data model

```mermaid
classDiagram
  Tester --> ResultGenerator
  UI --> Tester
  ResultGenerator --> UI
  class Tester{
    - input: string
    - startTime: time
    - endTime: time
    - errors: int
    + startTest()
    + endTest()
    + generateNewTest()
  }
  class ResultGenerator{
    - accuracy: float
    - totalTime: float
    + calculateAccuracy(totalChars: int, errors: int) float
    + calculateTotalTime(startTime: time, endTime: time) float
    - updateUI()
  }
  class UI{
    +updateDisplay()
  }

```
