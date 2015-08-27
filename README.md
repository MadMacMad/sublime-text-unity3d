# sublime-text-3
## Using Sublime Text as a script editor with Unity3d

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
```
cd ~/.config/sublime-text-3/Packages/User/
```
#### Clone the Package
```
git clone git@github.com:thicaso/sublime-text-3.git .
```
