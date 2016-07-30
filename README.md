###PluralSight Download Bookmarklet.

####Just Drag and Drop following code to bookmarks bar.

  [PluralSight SaveAs]: javascript:(function(){var moduleName = document.getElementsByClassName(&quot;selected watched&quot;)[0].parentElement.parentElement.getElementsByTagName(&quot;h2&quot;)[0].innerText;var clipName = document.getElementsByClassName(&quot;selected watched&quot;)[0].getElementsByTagName(&quot;h3&quot;)[0].innerText;var link = document.createElement('a');link.download = document.title + &quot;_&quot; + moduleName + &quot;_&quot; + clipName;fileContents = document.getElementsByTagName('video')[0].src;link.href = 'data:,' + fileContents;link.click();})();

```javascript
javascript:(function(){var moduleName = document.getElementsByClassName("selected watched")[0].parentElement.parentElement.getElementsByTagName("h2")[0].innerText;var clipName = document.getElementsByClassName("selected watched")[0].getElementsByTagName("h3")[0].innerText;var link = document.createElement('a');link.download = document.title + "_" + moduleName + "_" + clipName;fileContents = document.getElementsByTagName('video')[0].src;link.href = 'data:,' + fileContents;link.click();})();
```
Works only for Current Video you are viewing on pluralsight video page. Make sure only current Module is expanded in Sidebar of Pluralsight Player.

This will save url to txt file with Filename in format "CourseName || ModuleName || ClipName".txt

Later you can download video with your favourite downloader ( eg: axel or wget)

Chill !!
