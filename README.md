AlloyCustomFonts
================

Example of how to incorporate custom fonts with Titanium SDK 3.1.1

In an effort to put all of this information into one place, and into a working example I have tried to create a simple set of notes and working code to add custom fonts to the latest ( 3.1.1 ) Titanium Appcelerator Alloy application.

Here is what I needed to do to get this working:

1) download some fonts.  fontsquirrel.com has some good ones.  You can use either ttf or otf and I have used both in this example.

2) create the following directory path:   app/assets/fonts

3) copy your .ttf and .otf files to that directory

4) edit the xml portion of the tiapp.xml file and add the following at the same level as iphone:
    <ios>
        <plist>
          <dict>
            <key>UIAppFonts</key>
            <array>
              <string>fonts/RenStimpyFont.ttf</string>
              <string>fonts/Montez-Regular.ttf</string>
              <string>fonts/GoodDog.otf</string>
            </array>
          </dict>
        </plist>
      </ios>

5) create an app.tss file in the styles directory.  Technically you could have used the index.tss for this since you are adding the fonts to that view.

6) add the following as an example, but see the app.tss file in the project
".label1Style": {
  color: "#f00",
  top: 10,
  textAlign: 'center',
  font:{fontFamily:'Ren & Stimpy', fontSize: 27},
    shadowColor: '#eee',
    shadowOffset: {x:0,y:1}
  
},

this will create a custom style for a red 'Ren & Stimpy' style.

6) in the index.xml file add the class style name to the Label element:
        <Label class="label1Style">I am Window 1</Label>

That should be it.  If you compile the application project, there should be 3 tab, each with the label using a different font.

