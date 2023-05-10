# Flutter SMS Autofill

For iOS, this package is not needed as the SMS autofill is provided by default, but not for Android, that's where this package is useful.

No permission to read SMS messages is asked to the user as there no need thanks to SMSRetriever API.

## Usage

You have two widgets at your disposable for autofill an SMS code, PinFieldAutoFill and TextFieldPinAutoFill.

Just before you sent your phone number to the backend, you need to let the plugin know that it needs to listen for the SMS with the code.

To do that you need to do:

   ```await SmsAutoFill().listenForCode();```

This will listen for the SMS with the code during 5 minutes and when received, autofill the following widget.

### PinFieldAutoFill

   ```
   PinFieldAutoFill(
                decoration: // UnderlineDecoration, BoxLooseDecoration or BoxTightDecoration see https://github.com/TinoGuo/pin_input_text_field for more info,
                currentCode: // prefill with a code
                onCodeSubmitted: //code submitted callback
                onCodeChanged: //code changed callback
                codeLength: //code length, default 6
              ),
   ```

### TextFieldPinAutoFill

   ```
   TextFieldPinAutoFill(
                decoration: // basic InputDecoration
                currentCode: // prefill with a code
                onCodeSubmitted: //code submitted callback
                onCodeChanged: //code changed callback
                codeLength: //code length, default 6
              ),
   ```


