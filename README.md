###PluralSight Download Bookmarklet.

####Just create new bookmark in bookmarks bar with follwing code.

```javascript
javascript:(function(){var module = document.getElementsByClassName("selected watched")[0].parentElement.parentElement;var moduleName = module.getElementsByTagName("h2")[0].innerText;var clip = document.getElementsByClassName("selected watched")[0];var clipName = clip.getElementsByTagName("h3")[0].innerText;var clipIndex = 001;while( (clip = clip.previousSibling) != null ) clipIndex++;var moduleIndex = 101;while( (module = module.previousSibling) != null ) moduleIndex++; var clipFullName = document.title + "/" + moduleIndex + "_" + moduleName + "/" + clipIndex + "_" + clipName;var linkName = document.createElement('a');var linkFile = document.createElement('a');var videolink = document.getElementsByTagName('video')[0].src ;var videoName = videolink.split("/").pop().split('#')[0].split('?')[0].split('.')[0];linkFile.href = videolink ;linkName.download = videoName +".txt";linkName.href = 'data:,' + clipFullName.replace(/ /g,"_");linkFile.download = videoName ;linkName.click();linkFile.click();})();
```
Works only for Current Video you are viewing on pluralsight video page. 

This will save video and txt file with same Filename which contains clip name in "CourseName/ModuleName/ClipName" format.

later you can simply generate folder structure using shell script below.Assuming ls *.txt are all txtfiles download using bookmarklet.
```
ls *.txt | while read i ; do  if [ ! -d $(cat "$i" | awk -F'/' '{print $1"/"$2}' | uniq) ] ; then mkdir -p "$(cat "$i" | awk -F'/' '{print $1"/"$2}' | uniq)" ; fi  ;cp -v $(basename "$i" ".txt").mp4 $(cat "$i").mp4 ;done
```




Cheers !!
