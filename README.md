# UITestExample

```Swift
import XCTest
class StarFarmerTests: XCTestCase {
    
    var farm: Myfarm! //declare etmek
    
    override func setUpWithError() throws {
        
        farm = Myfarm(name: "xyz")
        // Put setup code here. This method is called before the invocation of each test method in the class.
    }

    func testAddAnimal() throws {
        //MARK: Given
        let animalName = "cow"
        //MARK: When
        let water = farm.addAnimal(typeOfAnimal: animalName)
        //MARK: Then
        XCTAssertEqual(farm.animals.count, 1)
        XCTAssertEqual(water, 5)
        
        // This is an example of a functional test case.
        // Use XCTAssert and related functions to verify your tests produce the correct results.
        // Any test you write for XCTest can be annotated as throws and async.
        // Mark your test throws to produce an unexpected failure when your test encounters an uncaught error.
        // Mark your test async to allow awaiting for asynchronous code to complete. Check the results with assertions afterwards.
    }
    func testAddWater() throws {
        
        let water = 100
        
        farm.addWater(water: water)
        
        XCTAssertEqual(farm.totalWaterIntheTank, 600)
    }

}
