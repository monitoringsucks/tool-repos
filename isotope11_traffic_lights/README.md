[github](https://github.com/johndavid400/Isotope11_traffic_lights)

# Monitoring your Continuous Integration Server with Traffic Lights and an Arduino
### A way for Isotope11 to visually monitor the testing status of its many software projects.
Today I am going to walk through our recent continuous integration Traffic light
notifier project that we just finished at the office. This project stemmed from
my company's desire to immediately know if a developer has broken a software
project, and what better way to do that than to have a huge red light flashing
in your face. We connected an old salvaged traffic light fixture to our Jenkins
CI-server that monitors the testing status of all of our current software
projects. If all our tests are passing, the light stays green, if any test fails
the light turns red to provide a visual notification of a problem. While Jenkins
is running a test suite on any project, the yellow light will flash to let us
know of the activity.

