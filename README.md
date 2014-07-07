uDMX
====

**uDMX** is a simple C# class to control [uDMX](http://www.illutzmination.de/udmx.html) device from .NET application. It was tested in *Windows* and *Linux/Mono*.

Example
-------

	using(uDMX dmx = new uDMX())
	{
		if (dmx.IsOpen) 
		{
		  // Set channel 0 to value 127
		  dmx.SetSingleChannel (0, 127);            
		  // Set three channels, starting with channel 0
		  byte[] values = new byte[] { 0xFF, 0xAA, 0x05 }      
		  dmx.SetChannelRange(0, values);
		}
	}

Prerequsites
------------

- [LibUsbDotNet](http://sourceforge.net/projects/libusbdotnet/) .NET wrapper for *libusb*
- [libusb-win32](http://sourceforge.net/projects/libusb-win32/) for Windows
- [libusb](http://www.libusb.org/) for Linux 

Known issues
------------

- **uDMX.SetChannelRange()** does not work properly in Linux :(
