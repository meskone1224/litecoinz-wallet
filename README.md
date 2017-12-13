# Desktop GUI Wallet for [LitecoinZ](http://litecoinz.info/)[®](#disclaimer)

## Graphical user interface wrapper for the [LitecoinZ](http://litecoinz.info/)[®](#disclaimer) command line tools

This program provides a Graphical User Interface (GUI) for the LitecoinZ client tools that acts as a wrapper and 
presents the information in a user-friendly manner.

![Screenshot](https://github.com/vaklinov/litecoinz-wallet/raw/master/docs/LitecoinZWallet.png "Main Window")

## Building, installing and running the Wallet GUI

Before installing the Desktop GUI Wallet you need to have LitecoinZ up and running. The following [guide](https://github.com/litecoinz-project/litecoinz/wiki/1.0-User-Guide) 
explains how to set up [LitecoinZ](http://litecoinz.info/). 

**For security reasons it is recommended to always build the GUI wallet program from GitHub**
**[source](https://github.com/litecoinz-project/litecoinz-wallet/archive/master.zip).**

1. Operating system and tools

   As of Dec 2017 (LitecoinZ v1.0.13) this program is mostly tested on Linux and Mac OS X
   (same limitation as [LitecoinZ](http://litecoinz.info/)) with experimental support for Windows.
   The Linux tools you need to build and run the Wallet GUI are Git, Java (JDK7 or later) and
   Ant. If using Ubuntu Linux, they may be installed via command: 
   ```
   user@ubuntu:~/build-dir$ sudo apt-get install git default-jdk ant
   ``` 
   For RedHat/CentOS/Fedora-type Linux systems the command is (like):
   ```
   user@centos:~/build-dir$ sudo yum install java-1.8.0-openjdk git ant 
   ```
   The name of the JDK package (`java-1.8.0-openjdk`) may vary depending on the Linux system, so you need to
   check it, if name `java-1.8.0-openjdk` is not accepted.
   If you have some other Linux distribution, please check your relevant documentation on installing Git, 
   JDK and Ant. The commands `git`, `java`, `javac` and `ant` need to be startable from command line 
   before proceeding with build.

2. Building from source code

   As a start you need to clone the litecoinz-wallet Git repository:
   ```
   user@ubuntu:~/build-dir$ git clone https://github.com/litecoinz-project/litecoinz-wallet.git
   ```
   Change the current directory:
   ```
   user@ubuntu:~/build-dir$ cd litecoinz-wallet/
   ```
   Issue the build command:
   ```
   user@ubuntu:~/build-dir/litecoinz-wallet$ ant -buildfile ./src/build/build.xml
   ```
   This takes a few seconds and when it finishes, it builds a JAR file `./build/jars/LitecoinZSwingWalletUI.jar`. 
   You need to make this file executable:
   ```
   user@ubuntu:~/build-dir/litecoinz-wallet$ chmod u+x ./build/jars/LitecoinZSwingWalletUI.jar
   ```
   At this point the build process is finished the built GUI wallet program is the JAR 
   file `./build/jars/LitecoinZSwingWalletUI.jar`

3. Installing the built LitecoinZ GUI wallet

  3.1. If you have built LitecoinZ from source code:

   Assuming you have already built from source code [LitecoinZ](https://github.com/litecoinz-project/litecoinz) in directory `/home/user/litecoinz/src` (for 
   example - this is the typical build dir. for LitecoinZ v1.0.13) which contains the command line tools `litecoinz-cli` 
   and `litecoinzd` you need to take the created file `./build/jars/LitecoinZSwingWalletUI.jar` and copy it 
   to directory `/home/user/litecoinz/src` (the same dir. that contains `litecoinz-cli` and `litecoinzd`). Example copy command:
   ```
   user@ubuntu:~/build-dir/litecoinz-wallet$ cp ./build/jars/LitecoinZSwingWalletUI.jar /home/user/litecoinz/src    
   ```

  3.2. If you have downloaded the [LitecoinZ Binary distribution](http://litecoinz.info/download.html):

   Assuming you have already downloaded the file `litecoinz-1.0.x-linux64.tar.gz` which contains the command 
   line tools `litecoinz-cli` and `litecoinzd` and after decompressing it they are in a directory like 
   `/home/user/litecoinz-1.0.x/bin/` take the created file `./build/jars/LitecoinZSwingWalletUI.jar` and copy it 
   to directory `/home/user/litecoinz-1.0.x/bin/` (the same dir. that contains `litecoinz-cli` and `litecoinzd`). 
   Example copy command:
   ```
   user@ubuntu:~/build-dir/litecoinz-wallet$ cp ./build/jars/LitecoinZSwingWalletUI.jar /home/user/litecoinz-1.0.13/bin/    
   ```
   
  3.3. If you have installed the LitecoinZ [binary packages](https://github.com/litecoinz-project/litecoinz/wiki/Debian-binary-packages)

   The command line tools `litecoinz-cli` and `litecoinzd` are placed by the package installer in:
   ```
   /usr/bin/litecoinz-cli
   /usr/bin/litecoinzd
   ```
   The LitecoinZ GUI wallet knows how to find them there. You may place the file  `./build/jars/LitecoinZSwingWalletUI.jar`
   anywhere in your `/home` directory that you find convenient and start it from there.

4. Running the installed LitecoinZ GUI wallet

   Before running the GUI you need to start litecoinzd (e.g. `litecoinzd --daemon`). The wallet GUI is a Java program packaged 
   as an executable JAR file. It may be run from command line or started from another GUI tool (e.g. file manager). 
   Assuming you have already installed [LitecoinZ](http://litecoinz.info/) and the GUI Wallet `LitecoinZSwingWalletUI.jar` in 
   directory `/home/user/litecoinz/src` one way to run it from command line is:
   ```
   user@ubuntu:~/build-dir/litecoinz-wallet$ java -jar /home/user/litecoinz/src/LitecoinZSwingWalletUI.jar
   ```
   If you are using Ubuntu (or similar ;) Linux you may instead just use the file manager and 
   right-click on the `LitecoinZSwingWalletUI.jar` file and choose the option "Open with OpenJDK 8 Runtime". 
   This will start the LitecoinZ GUI wallet.

### License
This program is distributed under an [MIT License](https://github.com/litecoinz-project/litecoinz-wallet/raw/master/LICENSE).

### Disclaimer

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

### Known issues and limitations

1. Issue: Wallet versions 0.58 and below, when running on systems with (typically non-western) locales that
redefine the decimal point in the OS locale settings, have problems with updating the GUI wallet state. 
A workaround is to change the [locale settings](https://windows.lbl.gov/software/optics/5-1-2/Optics4.jpg) to have dot as decimal separator.
2. Limitation: wallet encryption has been temporarily disabled in the LitecoinZ Desktop GUI Wallet.
3. Issue: the GUI wallet does not work correctly if litecoinzd is started with a custom data directory, like:
`litecoinzd -datadir=/home/data/whatever` This will be fixed in later versions.
4. Issue: GUI data tables (transactions/addresses etc.) allow copying of data via double click but also allow editing. 
The latter needs to be disabled. 
5. Limitation: The list of transactions does not show all outgoing ones (specifically outgoing Z address 
transactions). 
6. Limitation: The CPU percentage shown to be taken by litecoinzd on Linux is the average for the entire lifetime 
of the process. This is not very useful. This will be improved in future versions.
