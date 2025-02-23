# JS-Array-Problems





// Reveres an Array

var arr = [1,2,3,4,5]
var left = 0
var right = arr.length-1 //5-1=4

while (left<right)
{
    var temp = arr[left] // arr[0] = 1
    arr[left] = arr[right]
    arr[right] = temp

    left++
    right--
    
}
console.log(arr)

//Flattern Array

var arr = [1,[2,3],4,[5,[6,7],8,9],10]

var result = []

function flat(arr)
{ 

    arr.forEach(item => {
        
        if(Array.isArray(item))
        { 
            flat(item)
        }
        else { 
            result.push(item)
        }
        
    });

}
flat(arr)
console.log(result)

//Remove Duplicate

var arr = [1,2,3,4,5,5,4,3,2,1]

function removeduplicate(arr)
{
    return [...new Set(arr)]
}

console.log(removeduplicate(arr))

//Find Largest Number in array

var arr = [20,56,88,102,44]
var maximum = Math.max(...arr)
console.log(maximum)

var arr = [10,20,30]
var largest = arr[0]

//Tradional method to find maximun value in array
for (count=1;count<arr.length;count=count+1)
{
    if(arr[count]>largest)
    {
        largest=arr[count]
    }
}
console.log(largest)

//Group array of Obects by Property

var myarr = [
    {
        name: "Fruits", value:"Orange"
    },
    {
        name: "Fruits", value: "Orange"
    },
    {
        name: "Vegetables", value: "Tomato"
    }
]


function groupType(myarr)
{
    var result = [{}]

    for(var key of myarr)
    {
        var type = key.name

        if (!result[0][type])
        {
            result[0][type] = []
        }
        result[0][type]=[
            ...result[0][type],
            key
        ]
    }

    return result

}

console.log(groupType(myarr))

//Intersection of two arrays

var arr1 = [1,2,3,4]
var arr2 = [3,5,2,8]

var s1 = new Set (arr1)
var s2 = new Set (arr2)

var intersection = [...s1].filter(num => s2.has(num))
console.log(intersection)


