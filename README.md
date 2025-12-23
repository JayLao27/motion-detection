# SMS Motion Detection Arduino Project

A motion detection system using a PIR sensor with SMS alerts via SIM800L module.

## SMS Motion Detection (`sms-interrupt.ino`)

After confirming your PIR sensor works, you can implement the SMS alert system:

### Hardware Setup
- PIR Sensor → Pin 2
- LED → Pin 13
- SIM800L RX → Pin 10
- SIM800L TX → Pin 11

### Implementation Steps (W/SIM800L)

1. **Configure Phone Number**: Update `SMS_TARGET` in the code with your phone number (format: "+1234567890")
2. **Insert SIM Card**: Place an active SIM card into the SIM800L module
3. **Upload Code**: Upload `sms-motion.ino` to your Arduino board
4. **Wait for Network Connection**: 
   - Open Serial Monitor (115200 baud)
   - **You must wait until the SIM800L blinks every 3 seconds** - this indicates it has connected to the network
   - Watch for "Network connected!" message in Serial Monitor
5. **Test Motion Detection**: 
   - Once connected, move in front of the PIR sensor
   - When motion is detected, the system will automatically send an SMS to the number you specified in `SMS_TARGET`
   - You should receive a text message saying "Motion Detected!"
  - Serial Monitor will show "Motion detected!" and "SMS sent!" messages

   <img src="https://imgur.com/Up3RDqe.jpg" width="500" alt="Arduino IDE Serial Monitor displaying motion detection logs with timestamps, showing Motion detected! and SMS sent! messages confirming successful PIR sensor trigger and SMS transmission via SIM800L module">


### Important Notes
- The SIM800L must complete network registration before motion detection will trigger SMS alerts
- The blinking pattern (every 3 seconds) confirms successful network connection
- Make sure your SIM card has active service and SMS capability

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
