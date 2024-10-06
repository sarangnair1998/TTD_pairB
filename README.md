# TDD Pair A
# C++ Boilerplate v2 Badges
![CICD Workflow status](https://github.com/keyurborad5/TTD_pairA/actions/workflows/run-unit-test-and-upload-codecov.yml/badge.svg) [![codecov](https://codecov.io/gh/keyurborad5/TTD_pairA/branch/main/graph/badge.svg)](https://codecov.io/gh/keyurborad5/TTD_pairA) [![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)


## Overview
## Part1
- Driver : Keyur Borad - @KeyurBorad5
- Navigator: Uthappa Madettira - @Uthappa13

## Program
- This PID controller has preset KP,KI,KD values
- It has a preset actual/present speed, which is 100
- Once the program is executed, it asks for user input to enter desire speed
- Code calculates the speed to be achieved after one time step as here we are calculating only for 1 time step for simplicity.
- For example is entered desire speed is 50 then output speed would be calculated based on error difference of actual(100) and desired speed(50)


## Run program
```bash
# Change the directory to pbm1_4
  cd cpp-boilerplate-v2
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed
# Set the build type to Debug and WANT_COVERAGE=ON
  cmake -D WANT_COVERAGE=ON -D CMAKE_BUILD_TYPE=Debug -S ./ -B build/

#************CODE COVERAGE REPORT *********************
# Now, do a clean compile, run unit test, and generate the covereage report of unit tests
  cmake --build build/ --clean-first --target all test_coverage
# open a web browser to browse the test coverage report
  open build/test_coverage/index.html

  # to see the code coverage of shell-app
  # Now, do another clean compile, run shell-app, and generate its covereage report
  cmake --build build/ --clean-first --target all app_coverage
# open a web browser to browse the test coverage report
  open build/app_coverage/index.html
#************  END ****************

#************RUN UNIT TEST *********************
# TO run test case
  ctest --test-dir build/
#************  END ****************

#************RUN SHELL-APP *********************
# Run program:
  ./build/app/shell-app

# Asks for enter Desire speed
# Enter numeric desired speed
# you will receive an output speed that is cal after one iteration/time step of the PID controller. (Here actual speed is set to 100)
#************  END ****************

#************Build Doxygen docs*********************
# Build docs:
  cmake --build build/ --target docs
  # open a web browser to browse the doc
  open docs/html/index.html
#************  END ****************

#************Remove Doxygen docs*********************
# Clean
  cmake --build build/ --target clean
#************  END ****************

#************Remove build folder*********************
# Clean and start over:
  rm -rf build/
#************  END ****************
