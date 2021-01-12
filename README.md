# How to connect to an Android emulator from one PC to other.

## Steps

- Open an Android emulator device.
- Check its port.
- Run emulator server.
- Connect client PC to server emulator.


### Check emulator port
Running `adb devices` the result should show you something like **"emulator-[port]   device"**

### Run Server
To run the emulator as a server we will be using a nice tutorial from [hasper.info by Philipp Hasper:](https://hasper.info/remote-android-emulator/).

Download the [PortForward](http://www.quantumg.net/portforward.php) windows binary and then run on your terminal:
 `~\trivial_portforward\trivial_portforward.exe [emulator-port] 127.0.0.1 5555`

### Connect client
Now, on your client PC, run `adb kill-server` & `adb connect [server-pc-IP]:[emulator-port]`.
If everything goes well, the terminal should show you a message like: 
**"connected to [server-pc-IP]:[emulator-port]"**.
And on the server side you should see:
** "received connection from [client-pc-IP]
connection to 127.0.0.1:5555 established"**

If you are having problems trying to connect the client with the emulator:
- Use an emulator that doesn't use the Google APIs.
- Run `ping [server-pc-IP]` just to be sure that the connection is stable.
- Be sure that the emulator network connection is stable.

If after all this you still facing some issues please let me know: lucasmontanari.97@gmail.com.
