###PluralSight Download Bookmarklet.

####Just create new bookmark in bookmarks bar with follwing code.

```javascript
javascript:(function(){var moduleName = document.getElementsByClassName("selected watched")[0].parentElement.parentElement.getElementsByTagName("h2")[0].innerText;var clipName = document.getElementsByClassName("selected watched")[0].getElementsByTagName("h3")[0].innerText;var link = document.createElement('a');link.download = document.title + "_" + moduleName + "_" + clipName;fileContents = document.getElementsByTagName('video')[0].src;link.href = 'data:,' + fileContents;link.click();})();
```
Works only for Current Video you are viewing on pluralsight video page. Make sure only current Module is expanded in Sidebar of Pluralsight Player.

This will save url to csv file with Filename in format "CourseName_ModuleName_ClipName".csv and content in 
"CourseName,ModuleNumber,ModuleName,ClipNumber,ClipName,ClipURL" format.

Later you can download video with your favourite downloader ( eg: curl or wget)

Cheers !!
