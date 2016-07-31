###PluralSight Download Bookmarklet.

####Just create new bookmark in bookmarks bar with follwing code.

```javascript
javascript:(function(){var module =  document.getElementsByClassName("selected watched")[0].parentElement.parentElement;var moduleName = module.getElementsByTagName("h2")[0].innerText;var clip = document.getElementsByClassName("selected watched")[0];var clipName = clip.getElementsByTagName("h3")[0].innerText;var clipIndex = 001;while( (clip = clip.previousSibling) != null ) clipIndex++;var moduleIndex = 101;while( (module = module.previousSibling) != null ) moduleIndex++; var clipFullName = document.title + "_" + moduleIndex + "_" + moduleName + "_" + clipIndex + "_" + clipName;var link = document.createElement('a');link.download = clipFullName+".csv";fileContents = document.title + "," + moduleIndex + "," + moduleName + "," + clipIndex + "," + clipName + "," + document.getElementsByTagName('video')[0].src;link.href = 'data:,' + fileContents;link.click();})();
```
Works only for Current Video you are viewing on pluralsight video page. Make sure only current Module is expanded in Sidebar of Pluralsight Player.

This will save url to csv file with Filename in format "CourseName_ModuleName_ClipName".csv and content in 
"CourseName,ModuleNumber,ModuleName,ClipNumber,ClipName,ClipURL" format.

Later you can download video with your favourite downloader ( eg: curl or wget)

Cheers !!
