# Setting up SonarQube code quality management platform 

SonarQube software (previously called Sonar) is an open source quality management platform, dedicated to continuously analyze and measure technical quality.

## Requirements

- Java 8 installed
- Add JAVA_HOME to PATH
- .NET framework 4 and/or above installed
- Add MSBuild 14.0 to PATH

## Installation

- Download SonarQube 6.7.1 (LTS *) https://www.sonarqube.org/downloads/
- Extract .zip folder you downloaded to `C:/SonarQube`
- Start Sonar server by running `C:\SonarQube\bin\windows-x86-xx\StartSonar.bat` or you can install Windows Service by running `C:\SonarQube\bin\windows-x86-64\InstallNTService.bat` (make sure to run Windows Service - SonarQube)
- After SonarQube is up and running go to web browser and hit: http://localhost:9000
- Login with admin/admin credentials
- Create a SonarQube project
- At the last step, SonarQube will give you some commands, make sure to note them somewhere, you'll need them later
- Now download scanner for MSBuild from https://github.com/SonarSource/sonar-scanner-msbuild/releases
- Extract .zip of scanner you downloaded to `C:/SonarQubeScanners`
- Add SonarQube.Scanner.MSBuild.exe folder `C:/SonarQubeScanners` to the PATH
- Now it's time to run SonarQube Analyzer

## Usage

- Open CMD
- Run the first command (change {HASH} to your project hash and {PROJECT_NAME} with the name of the project in SonarQube admin panel)
`SonarQube.Scanner.MSBuild.exe begin /k:"{PROJECT_NAME}" /d:sonar.host.url="http://localhost:9000" /d:sonar.login="{HASH}"`
- Run the second command with project file (change {SOLUTION/OR_PROJECT_FILE} tp folder with .sln/.cspj file)
`MsBuild.exe {SOLUTION/OR_PROJECT_FILE} /t:Rebuild`
- Run the third command (change {HASH} to your project hash)
`SonarQube.Scanner.MSBuild.exe end /d:sonar.login="{HASH}"`

## Links

- [SonarQube documentation](https://docs.sonarqube.org)                    
