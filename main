function * subsets(array, offset = 0) {
    while (offset < array.length) {
        let first = array[offset++];
        for (let subset of subsets(array, offset)) {
            subset.push(first);
            yield subset;
        }
    }
    yield [];
}

function getSubsets(inputArray) {
    const result = [];

    for (let subset of subsets(inputArray)) {
        result.push(subset);
    }

    return result;
}

function min(input) {
	if (toString.call(input) !== "[object Array]") {  
       return false;
	}
	return Math.min.apply(null, input);
}

var labels = ['S', 'M', 'L'];
var rangeNums = ['1', '2', '3', '4', '5'];
var bases = [35, 50, 65];
var moves = [86, 127, 184];
var ranges = [25, 76, 152, 203, 254];
var arr = [86, 127, 184, 25, 76, 152, 203, 254];
var arrSubsets = getSubsets(arr);
var subsetSums = [];

arrSubsets.sort((a,b) => a.length - b.length);

for (var i = 0; i < arrSubsets.length; i++) {
  subsetSums.push(arrSubsets[i].reduce((total, num) => total + num, 0));
}

for (var i = 0; i < bases.length; i++) {
	for (var j = 0; j < moves.length; j++) {
		for (var k = 0; k < ranges.length; k++) {
			var distance = bases[i] + moves[j] + ranges[k];
			var absArr = [];
      
			  for (var l = 0; l < subsetSums.length; l++) {
				absArr.push(Math.abs(distance - subsetSums[l]));
			  }
      
			  var minVal = min(absArr);
			  var comboIndex = absArr.findIndex(x => x === minVal);
			 
			 if (comboIndex < 0) {
			   console.log(subsetSums);
			   console.log(absArr);
			   console.log(distance);
			   console.log(minVal);
			   console.log(comboIndex);
			   continue;
			 }
     
			document.write("<p>" + labels[i] + " " + labels[j] + " " + rangeNums[k] + " - Sticks: " + arrSubsets[comboIndex].toString() + " - Diff: " + minVal + "</p>")
		}
	}
}
