# CadytsTests Getting Started 


## Run RailRaptor.java

 - Add network.xml, plans5.xml, vehicles.xml, transitSchedule1bus.xml, counts5.xml to input/bijoy. These are private files and are not included in this repo.
 - Select the root directory, right click it and select Run As -> Maven Clean
 - Select the root directory, right click it and select Run As -> Maven Build ... (type "package") into goals and run
 - Select RailRaptor.java in src>main>java>run and select Run Configurations. Make sure RailRaptor is selected
 - Goto Arguments Tab, and add input/bijoy/config.xml in the textarea
 - Run


## Dataset Issues
- Links in network.xml that have the same to and from node, seem to have been  given an id with `pt_` prefix when referenced in the transitScheduleBus.xml file. All records in transitScheduleBus.xml with "pt_"  where removed
- There was an invalid `dur` value in plans5.xml "0-1:0" probably meant to be 0:10
- Missing vehicles in vehicles.xml - we generated an xml file with 0-1999 bus id's 
- Invalid capacity values for many vehicles (type bus) we removed the transit module from config.xml (we didn't really solve this issue)


## Eclipse Setup

 - Download and install Eclipse https://www.eclipse.org/downloads/
 - Download and install Jave Runtime and JDK https://www.oracle.com/ca-en/java/technologies/downloads/

 - Clone this repo/branch
 ```bash
 git clone --branch bijoy-test https://github.com/uitr-lab/CadytsTests.git
```
 - Open folder in Eclipse

## Code/Config Updates from Cadyts https://github.com/ChristophTraf/CadytsTests
 ### pom.xml
  - replace maxsim dependency repo with https://repo.matsim.org/repository/matsim
  - set maxsim version to 11.0
  - add missing osgeo dependency https://repo.osgeo.org/repository/release/
  - remove scoped of cadytsIntegration dependency, was `test`

### RailRaptor.java
  - Organized imports
  - Initialize CadytsCarModule
  ```
  public void install() {
      ...
      this.install(new CadytsCarModule());
  }
  ```

### ParkingWalkRouting.java
  - add missing imports
  - add Abstract method getStageActivityTypes - likely due to using maxsim 11.0 

### Unit tests classes
  - Disabled all test - Cadyts repo references hard coded test input files that we do not have, and causes errors building

