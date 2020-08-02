# JSON-Examples

A repo for testing various JSON payloads. 


## Testing in Swift 

1. Navigate to the `.json` file you're interested in using.
2. Copy the `JSON` contents. 
3. Back in your Xcode project create a new file, select `Empty` file in the Xcode new file template.
4. Create a file with a similar name e.g `presidents.json`
5. Save this file in your App navigation folder. 
6. Use the `Bundle` class to read the `.json` file and parse to your Swift object. 

> Make sure the past `JSON` contents start on line 1 in your new file. It won't be valid `JSON` if there are new lines or any comments about the first encountered `JSON` open bracket. 

## Unit Test the JSON payload 

```swift 
func testModel() {
  // arrange
  let jsonData = """
  [{
     "number": 1,
     "president": "George Washington",
     "birth_year": 1732,
     "death_year": 1799,
     "took_office": "1789-04-30",
     "left_office": "1797-03-04",
     "party": "No Party"
   },
   {
     "number": 2,
     "president": "John Adams",
     "birth_year": 1735,
     "death_year": 1826,
     "took_office": "1797-03-04",
     "left_office": "1801-03-04",
     "party": "Federalist"
   }
  ]
  """.data(using: .utf8)!
  
  let expectedFirstPresident = "George Washington"
  
  // act
  do {
    let presidents = try JSONDecoder().decode([President].self, from: jsonData)
    let firstPresident = presidents[0]
    // assert
    XCTAssertEqual(firstPresident.president, expectedFirstPresident)
  } catch {
    XCTFail("decoding error: \(error)")
  }
}
```
