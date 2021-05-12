# On the VM, install MOSQUITTO (on the testbed it is already installed)
    sudo apt-get update 
    sudo apt-get install mosquitto

# Modify the configuration to allow connection from the tunslip interface
    sudo vim /etc/mosquitto/mosquitto.conf
    # Add the following lines to the file

      allow_anonymous true
      listener 1883 fd00::1

# Run MOSQUITTO
    sudo mosquitto -c /etc/mosquitto/mosquitto.conf

# Test it
    mosquitto_pub -h fd00::1 -t actuator -m ON

    mosquitto_sub -h fd00::1 -t status
