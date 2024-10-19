# grandMA2 Showfile Downgrade Macro

## Things user should know before using this macro

- Notice this macro is originally generated in version 3.3.4, which cannot be import in a lower version grandMA2 like v3.1.2.
- This is a macro collection which includes three macros: `Export High Show`, `Import Low Show`, and `Import User and User Profile`.
- When using this macro, make sure the USB drive is inserted and only **ONE** USE drive should be inserted.
- It is recommended to use a clean USB stick which will make whole process easier.

## How to use this macro

1. Import macro `Export High Show` in the version which your showfile are currently using. e.g. If your showfile version is v3.9.60, import marco `Export High Show` in this or higher version showfile directly.
2. It will take some time to execute macro `Export High Show`. After the macro is done executing, there will be several XML files generated which can be found in folders like "**importexport**", "**fixture_layers**", and "**library**". These files contain all the content of your exported showfile.
   > Tips: You use "Last Modified Date" to locate the XML files with nearest timestamp.
3. Open these XML files with a text editor like Notepad in Windows. At the beginning of each file, you will see version information like this:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <MA xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.malighting.de/grandma2/xml/MA" xsi:schemaLocation="http://schemas.malighting.de/grandma2/xml/MA http://schemas.malighting.de/grandma2/xml/3.9.60/MA.xsd" major_vers="3" minor_vers="9" stream_vers="0">
   ```

   This paragraph indicates your current showfile version. In this case, the showfile is v3.9.0:

   ```xml
   major_vers="3" minor_vers="9" stream_vers="0"
   ```

   And you should change the number to a lower version you want to convert. Let's say we want to downgrade this showfile to v3.3.4:

   ```xml
   major_vers="3" minor_vers="3" stream_vers="4"
   ```

   After you edit each file with a lower version number, remember to save the file.

4. Since we want to downgrade this showfile to v3.3.4, launch grandMA2 onPC 3.3.4.3 and create a new showfile with nothing inside.
5. In this new showfile, patch a dimmer with a Channel ID and DMX address that does not conflict with original higher version showfile. For example, you can patch a dimmer with Channel ID 34567 and DMX 234.56.
6. Import marco `Import Low Show` and execute in the current new showfile. It will take few minutes until the process is complete.
7. Moreover, if you want to also import your user and user profile from the higher showfile, you can also import macro `Import User and User Profile` and use it. Finally, log in to the user account to complete the downgrade process.

## Potential issues about this macro

- Some layouts assigned with the view will disappear.
- Default values set using presets will be lost.

To resolve these issues above, you have to configure it in the showfile again manually.
