# Wordle-Nytimes
example of match algorithm like in https://www.nytimes.com/games/wordle/index.html

```js

var keyword='notna';
let kwtemp;

function removeByIndex(str,index) {
      return str.slice(0,index) + str.slice(index+1);
}

function test2(str) {
	kwtemp=keyword;
	var arr = str.split('');
	for(i=0; i< str.length;i++){
		if(keyword[i]==str[i]) {
			arr[i]='green';
			kwtemp=removeByIndex(kwtemp,kwtemp.indexOf(str[i]))
		}
	}
	for(i=0; i< str.length;i++){
		if(kwtemp.indexOf(str[i])>-1 && arr[i].length<2) {
			arr[i]='yellow';
			kwtemp=removeByIndex(kwtemp,kwtemp.indexOf(str[i]))
		}
	}
	for(i=0; i< arr.length;i++){
		arr[i] = arr[i].length<2?'black':arr[i];
	}
	return arr;
}

test2('nnnnn')

```
