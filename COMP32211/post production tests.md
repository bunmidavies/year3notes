[[COMP32211]]

- not every manufactured chip will work correctly - post production tests exists to sort out which ones do and don't work
- this tests the synthesized netlist - the main issue is that there is a need to apply vectors to logic deep within sequential machines and units
- essentially, if you were testing a counter with 3 digits, you would ideally want to test every possible combination of digits, and this can be difficult to test efficiently

- ==Automatic Test Pattern Generation (ATPG)== exists for this reason - a large test set designed to provide comprehensive test coverage can be generated, but simultaneously this test set uses as few patterns as possible while guaranteeing complete testing

- ==Built-In Self Test (BIST)== typically involves a number of test patterns being stored on a chips ROM, or some sort of pseudo-random number generator - essentially, the SoC will have one or more processors which can be exploited for test purposes, meaning the ==chip can test itself==