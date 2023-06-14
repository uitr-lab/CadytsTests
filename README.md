# CadytsTests Getting Started 

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

## Data Issues
- 
