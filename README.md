# tippitytappity-design

tippitytappity is a program to practice typing


## Data model

```mermaid
classDiagram
  Tester --> ResultGenerator
  UI --> Tester
  UI --> User
  ResultGenerator --> UI
  testScoreStruct --> History
  ResultGenerator --> History
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
  class History{
    - history: Map<userID, testScoreStruct>
    + GetHistory(user: userID) vector<testScoreStruct>
    + AddHistory(user: userID, testHistory: testScoreStruct)
  }
  class testScoreStruct{
    + accuracy: float
    + totalTime: float
  }
  class User{
    - ID: userID
    + NewUser()
    + Login(username: string, password: string)
    + Logout()
  }

```
