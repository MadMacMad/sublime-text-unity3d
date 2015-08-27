# sublime-text-3
## Using Sublime Text as a script editor with Unity3d

##Kickstart:
```
cd %APPDATA%\Sublime Text 3\Packages\User
git clone git@github.com:thicaso/sublime-text-unity3d.git .
```

### Project Setup
* Open your project folder in File > Open Folder Select your Assets/Scripts folder
* Create your project in Tools > Save Project
* Edit your project in Toold > Edit Project
* Ignore .dll and .meta files:
```
{
	"folders":
	[
		{
			"path": "Assets/Scripts",
			"file_exclude_patterns":
			[
				"*.dll",
				"*.meta"
			]
		}
	]
}
```

### Install Package Control

Click in View > Show Console

Paste the code below:

```
import urllib.request,os,hashlib;
h = 'eb2297e1a458f27d836c04bb0cbaf282' + 'd0e7a3098092775ccb37ca9d6b2e4b7d'; 
pf = 'Package Control.sublime-package'; 
ipp = sublime.installed_packages_path(); 
urllib.request.install_opener( 
urllib.request.build_opener( 
urllib.request.ProxyHandler()) ); 
by = urllib.request.urlopen( 
'http://packagecontrol.io/' + 
pf.replace(' ', '%20')).read(); 
dh = hashlib.sha256(by).hexdigest(); 
print('Error validating download (got %s instead of %s),
please try manual install' % (dh, h)) 
if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by) 
```
### Setting C# Unity API Classes Autocompletion

Install the following Sublime Text packages by following the instructions on their respective Github README:
* "ApplySyntax",
* "C# Snippets",
* "Package Control",
* "Unity C# Snippets",
* "Unity Completions",
* "Unity Completions Light",
* "Unity3D",
* "Unity3D Build System",
* "Unity3D Reference Search",
* "Unity3D Shader Highlighter and Snippets",
* "Unity3D Snippets and Completes"

### Cloning the repository

#### Access the Package Directory

Windows: %APPDATA%\Sublime Text 3\Packages\User

OS X: ~/Library/Application Support/Sublime Text 3/Packages/User/

Linux: ~/.config/sublime-text-3/Packages/User/
```
cd ~/.config/sublime-text-3/Packages/User/
```

#### Clone the Package
```
git clone git@github.com:thicaso/sublime-text-unity3d.git .
```

###If you are in windows
Go to Preferences > Setting-User

Comment this line:
```
//"completesharp_mono_path": "/Applications/Unity/MonoDevelop.app/Contents/MacOS/bin/MonoDevelop"
```
####And modify the path of Unity Editor:
```
"folders": [
...
], //<- comma required
...
"settings": {
...

//Possible default directory paths for Unity:
//Windows: C:\Program Files\Unity\Editor\Data\
//Windows 64-bit: C:\Program Files (x86)\Unity\Editor\Data\
//Mac OS X: /Applications/Unity/Unity.app/Contents/Frameworks/
//Linux (default*): \\opt\\Unity\\Editor\\Data\\

"completesharp_assemblies": [
		"<path-to-Unity-folder>\\Managed\\UnityEngine.dll",

		"<path-to-Unity-folder>\\Managed\\UnityEditor.dll",

		"<path-to-Unity-folder>\\Mono\\lib\\mono\\unity\\UnityScript.dll",

		"<path-to-Unity-folder>\\Mono\\lib\\mono\\unity\\System.Core.dll",

		"<path-to-Unity-folder>\\Mono\\lib\\mono\\unity\\System.dll",

		"<path-to-Unity-folder>\\Managed\\nunit.framework.dll",

		"<path-to-Unity-folder>\\Mono\\lib\\mono\\unity\\mscorlib.dll",

		"<path-to-Unity-folder>\\Mono\\lib\\mono\\unity\\System.Core.dll",

		"<path-to-Unity-folder>\\Mono\\lib\\mono\\unity\\System.dll",
"${project_path:Library}\\ScriptAssemblies\\Assembly-CSharp.dll",

		"${project_path:Library}\\ScriptAssemblies\\Assembly-CSharp-Editor.dll",

		"${project_path:Library}\\ScriptAssemblies\\Assembly-UnityScript-Editor.dll",

		"${project_path:Library}\\ScriptAssemblies\\Assembly-CSharp-firstpass.dll"
	],

	"completioncommon_inhibit_sublime_completions": true,

	"completioncommon_shorten_names": true
}
```
