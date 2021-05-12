# IoT testbed workflow

# Copy the program you want to run
    scp -r -P 20XX -i ../testbed/key mqtt-lab-testbed/ user@iot.dii.unipi.it:~

# Connect to the testbed
    ssh -i ../testbed/key -p 20XX user@iot.dii.unipi.it

# Flash the program
    make TARGET=nrf52840 BOARD=dongle name-program.dfu-upload PORT=/dev/ttyACMXX

# Get the log
    make TARGET=nrf52840 BOARD=dongle login PORT=/dev/ttyACMXX

# If needed open another terminal and: (1) flash the border router on another mote and (2) run the connect-router
    make TARGET=nrf52840 BOARD=dongle border-router.dfu-upload PORT=/dev/ttyACMYY

    make TARGET=nrf52840 BOARD=dongle connect-router PORT=/dev/ttyACMYY

