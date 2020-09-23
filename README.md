<div align="center">

## BrowseForFolder


</div>

### Description

This one should behave like the FolderNameEditor class, but with public methods.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Mattias Eliasson](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/mattias-eliasson.md)
**Level**          |Beginner
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C\#
**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__10-3.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/mattias-eliasson-browseforfolder__10-375/archive/master.zip)





### Source Code

```
public class BrowseForFolder : FolderNameEditor {
	private FolderNameEditor.FolderBrowser fBrowser;
	public enum FolderBrowserStyles2 :int {
		BrowseForComputer = 0x00001000,
		BrowseForEverything = 0x00004000,
		BrowseForPrinter = 0x00002000,
		RestrictToDomain = 0x00000002,
		RestrictToFilesystem = 0x00000001,
		RestrictToSubfolders = 0x00000008,
		ShowTextBox = 0x00000010,
	}
	public enum FolderBrowserFolder2 {
		Desktop = 0x00000000,
		Favorites = 0x00000006,
		MyComputer = 0x00000011,
		MyDocuments = 0x00000005,
		MyPictures = 0x00000027,
		NetAndDialUpConnections = 0x00000031,
		NetworkNeighborhood = 0x00000012,
		Printers = 0x00000004,
		Recent = 0x00000008,
		SendTo = 0x00000009,
		StartMenu = 0x0000000B,
		Templates = 0x00000015,
	}
	public string Description {
		get {return fBrowser.Description;} set{fBrowser.Description = value;}
	}
	public string DirectoryPath { get{return fBrowser.DirectoryPath;} }
	protected FolderBrowserFolder2 StartLocation {
		get{return (FolderBrowserFolder2)(int)fBrowser.StartLocation;} set{fBrowser.StartLocation=(FolderBrowserFolder)(int)value;}
	}
	protected FolderBrowserStyles2 Style {
		get{return (FolderBrowserStyles2)(int)fBrowser.Style;} set{fBrowser.Style=(FolderBrowserStyles)(int)value;}
	}
	public DialogResult ShowDialog() {return fBrowser.ShowDialog();}
	public DialogResult ShowDialog(IWin32Window owner) {return fBrowser.ShowDialog(owner);}
	public BrowseForFolder() {
		fBrowser = new FolderBrowser();
	}
	~BrowseForFolder() {
		fBrowser.Dispose();
	}
}
```

