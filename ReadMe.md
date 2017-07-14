# Iteration and Arrays

In this lesson we will use and discover built-in methods to iterate through an array. Using our new skills we will build our own Recipe Generator that will help us create some dishes for a party we are planning.

JavaScript’s **built-in methods** are actions that can be performed on objects, which in this case are arrays. Built-in methods always contain a function which defines the action that is taken on the object.

As of ES5 (now supported by roughly 98% of browsers), JavaScript supplies a number of built-in methods for array iteration. In this lesson, we'll go through some of the most useful methods.

Click next to get started!

---

## Iterating through Arrays: a Refresher
We should all be pretty familiar with arrays but before we get too deep, here's a quick refresher.

Arrays are high-level, list-like objects. We can use them to store, organize, and retrieve data.

For example, arrays can contain a list of strings, numbers, boolean statements, other arrays, and objects.
	
	//Examples of Arrays
	var strings = ['Apple', 'Banana'];
	var numbers = [4, 9, 18, 43];
	var boolean = [true, false, true, true, true];
	var arrayOfarrays = [[0,1], [1,0], [1, 1]];
	var arrayOfobjects = [{food:'chicken', type:'meat', flavor:'savory', color:'white'}, {food:'apple', type:'fruit', flavor:'sweet', color:'red'}, {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'}, {food:'rice', type:'grain', flavor:'savory', color:'white'}]

Arrays can also contain a combination of the different types of data above.

As we mentioned, today we are going to learn some new methods for iterating through an array in order to store, find, retrieve, and manipulate the data it contains. 

You are already familiar with this concept because we have had some fun with loops in previous lessons. Remember that loops offer a quick and easy way to do something repeatedly a specified number of times. Essentially they allow us to iterate through things. Like arrays for example!

Typically we would use a for loop to iterate through an array, like below:

	// using a for loop to iterate through an array
	var food = ['chicken', 'apple', 'broccoli', 'rice'];
	for (var i = 0; i < food.length; i++) {
		console.log(food[i]);
	};

This code will iterate through our array of strings and print out each word in the array. 

Cool! Now it's your turn to give it a shot!

Let's do a quick exercise to make sure we remember how to use a for loop to iterate through an array.

##### Array and for loop Refresher Exercise

1. Create an array called `fridgeContents` and fill it with at least 4 things that are currently in your fridge right now.
2. Write a for loop to iterate through the array and print the results in the console.

		// your code should look like this
		var fridgeContents = ['item1', 'Item2', 'Item3', 'Item4'];
		for (var i = 0; i < fridgeContents.length; i++) {
			console.log(fridgeContents[i]);
		};

Amazing. You got this!

Ok so that is all well and good but as of ES5 we can do the same thing in a much cleaner and more legible way using built-in methods.

Click next to learn more about built in method for arrays.

---

## Introducing `.forEach()`

Introducing the `.forEach()` method. It's pretty awesome.

Remember, methods are the actions that can be performed on objects, in this case an array. 

`.forEach()` is a method that we can use to iterate through an array in place of a for loop. It takes a callback function as a parameter and will be called on each element of an array. Using `.forEach()`, we can loop through an array and execute a callback function once for each element in the array.

Pretty cool, right?

So here’s the old school way of handling an iteration with for loops:

	// using a for loop to iterate through an array
	var food = ['chicken', 'apple', 'broccoli', 'rice'];
	for (var i = 0; i < food.length; i++) {
		console.log(food[i]);
	};

And here’s how this same action can be rewritten using the built-in `.forEach()` method:

	//.forEach()
	var food = ['chicken', 'apple', 'broccoli', 'rice'];
	food.forEach(function(food) {
		console.log(food);
	});

Can you see how we have replaced our standard for loop? 

We have attached the method `.forEach()` to our array, and provided a callback function. The `.forEach()` method iterates once though the array and executes our callback function once on each element present, always in ascending order. 

When we use the `.forEach()` method, we pass a variable into our function representing the data we wish to retrieve, or the current value. In the example above, this variable is named `food`. We pass this variable into our function and then console.log its value, which is the value of the item in the array.

The callback function you provide can take a few arguments. Let's take a quick look at them:

+ currentValue - The value of the current element being processed in the array. 
+ index - The index of the current element being processed in the array. 
+ array - The array that `.forEach()` is being applied to.

You can find out more about `.forEach()` by [looking through the documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).

For now, we are going to focus on providing only currentValue to our callback function.

Ok, now you give it a try!

##### `.forEach()` Exercise

In the code editor you should see the for loop you just wrote:

	//var fridgeContents = ['item1', 'Item2', 'Item3', 'Item4'];
	for (var i = 0; i < fridgeContents.length; i++) {
		console.log(fridgeContents[i]);
	};

1. Take the for loop you just made and convert it using the `.forEach()`  method. Remember to provide a variable to your callback! It can be any word you like, but let’s use `food` for now.

		// your code should look like this
		var fridgeContents = ['item1', 'Item2', 'Item3', 'Item4'];
		fridgeContents.forEach(function(food) {
			console.log(food);
		});

Great job.
Doesn't that just make life easier? Look at how the `.forEach()`  method is so much cleaner and nicer to read than a for loop.

There are a lot of cool methods for arrays, and they all tend to make life a little easier. Let's go through some more of them! There are so many more to play with!

In the next section we will begin our final project for this course, making a recipe generator to help us build a Recipe for a party. As we do this we will use and become familiar with even more built-in methods to use with arrays.

Sounds fun doesn't it?
Yeah! So go ahead, click next to continue.

---

## Recipe Generator
It's time to build a Recipe generator!

You are having a party and are coming up with a Recipe based on ingredients your guests bring for the occasion. The following array contains objects that represent the ingredients your guests said they are planning to bring over. Each object also contains some key information about that ingredient, like type, flavor, and color.

	//Array of guestFoods
	var guestFoods = [
		{food:'chicken', type:'meat', flavor:'savory', color:'white'},
		{food:'apple', type:'fruit', flavor:'sweet', color:'red'},
		{food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},
		{food:'rice', type:'grain', flavor:'savory', color:'white'},
	]

You also have a bunch of ingredients in your fridge that you plan to use.

Before we get too far into making a Recipe, let's make sure we are including these items in our planning.

##### Array of Objects Refresher

1. Create a similar array to the one above. Title it `myFoods` and include in it 5 objects representing some of your favorite foods to have on hand.  Make sure to include the same properties as the objects in our existing array, including `food`, `type`, `flavor`, and `color`.

	//your array might look like this
	var myFoods = [  
    {food:'beef', type:'meat', flavor:'savory', color:'brown'},  
    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
    {food:'potato', type:'starch', flavor:'savory', color:'white'},  
	]

Awesome job.

Click next to continue.

---

## Recipe Generator: Combining Arrays

Now we have two arrays which contain our food items and some information about their properties. But we want to combine them into one array in order to move forward.

How can we combine our two arrays into a new one that includes all of our Recipe items? Surprise! There is a method for that!

As mentioned earlier in this lesson, there are many different built-in methods we can use to iterate through an array.  While some methods iterate through an array and return nothing, like `.forEach()`, other methods iterate through an array and return data, another array for example.

The [`.concat()` method](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat) is used to merge two or more arrays and return a new array. Perfect for our purposes!  In order to combine two arrays using the `.concat()` method we would need to create a new array using the following syntax: `var arr3 = arr1.concat(arr2);` 

Do you think you can figure out how to use this method to combine our two arrays? I bet you can! 

Let's give it a shot.

##### `.concat()` Exercise

You now have two arrays in your code window. One called `guestFoods` and one called `myFoods`.

	// two arrays
	var guestFoods = [  
	    {food:'chicken', type:'meat', flavor:'savory', color:'white'},  
	    {food:'apple', type:'fruit', flavor:'sweet', color:'red'},  
	    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'rice', type:'starch', flavor:'savory', color:'white'},  
		] //provided array
	var myFoods = [  
	    {food:'beef', type:'meat', flavor:'savory', color:'brown'},  
	    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
	    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'potato', type:'starch', flavor:'savory', color:'white'},  
		] //user array (user makes this)

1. Use `.concat()` to combine the `guestFoods` and `myFoods` arrays into a new array titled `allFoods`.

		//your code should look like this
		var guestFoods = [  
		    {food:'chicken', type:'meat', flavor:'savory', color:'white'},
		    {food:'apple', type:'fruit', flavor:'sweet', color:'red'}, 
		    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},
		    {food:'rice', type:'starch', flavor:'savory', color:'white'},
			] //provided array
		var myFoods = [  
		    {food:'beef', type:'meat', flavor:'savory', color:'brown'},
		    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},
		    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},
		    {food:'potato', type:'starch', flavor:'savory', color:'white'},
			] //user array (user makes this)

		var allFoods = guestFoods.concat(myFoods);

2. Great now console.log the new array, `allFoods`.

		//your code should look like this
		var guestFoods = [  
		    {food:'chicken', type:'meat', flavor:'savory', color:'white'},
		    {food:'apple', type:'fruit', flavor:'sweet', color:'red'},
		    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},
		    {food:'rice', type:'starch', flavor:'savory', color:'white'},
			] //provided array
		var myFoods = [  
		    {food:'beef', type:'meat', flavor:'savory', color:'brown'},
		    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},
		    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},
		    {food:'potato', type:'starch', flavor:'savory', color:'white'},
			] //user array (user makes this)

		var allFoods = guestFoods.concat(myFoods);
		console.log(allFoods);
	
Amazing! Now that we have all of our food organized in one place we can start generating our Recipe and choosing specific ingredients.

Click next to continue.

---

## Recipe Generator: Filtering our Ingredients

There is a guest coming to the party who is vegetarian and you want to sort out only the food that they can eat, i.e. the food that is not meat.

Let's use a built-in method to iterate through our array and filter out the results that aren't the type 'meat'.

But first let's take a moment the remember how we would do this using a standard for loop.
It would look something like this:

	// for loop filter and push
	var foodObjects = [
			{food:'chicken', type:'meat', flavor:'savory', color:'white'},
			{food:'apple', type:'fruit', flavor:'sweet', color:'red'},
			{food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},
			{food:'rice', type:'grain', flavor:'savory', color:'white'},
		]
	var vegetarianItems = [];
	for (var i = 0; i < foodObjects.length; i++) {
		if (foodObjects[i].type != 'meat'){
			vegetarianItems.push(foodObjects[i].food);
		}
	};

There's a lot of code in there. I bet we could make this shorter by using an array method to filter our results and sort them into a new array. 

Can you find a method that will do just this by [looking through the documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)?

Did you find it?

The `.filter()` method should do the trick! This method creates a new array with all elements from the current array that pass a test which is carried out by the provided callback function. Let's give it a try!

##### `.filter()` Exercise

In your editor you should see the `allFoods` array that we made in the last excersize

	// your array should look like this
	allFoods = [  
    {food:'chicken', type:'meat', flavor:'savory', color:'white'},  
    {food:'apple', type:'fruit', flavor:'sweet', color:'red'},  
    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},  
    {food:'rice', type:'starch', flavor:'savory', color:'white'},  
	{food:'beef', type:'meat', flavor:'savory', color:'brown'},  
    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
    {food:'potato', type:'starch', flavor:'savory', color:'white'}  
	]



1. Create a variable under the array and call it `sortedType` and assign it the value “meat”.

		// your code should look like this
		var sortedType = 'meat';

2. Use the `.filter()` method to sort through `allFoods` and filter out the results that do not equal `sortedType` into an array called `ingredients`.

		// your code should look like this
		var sortedType = 'meat';
		var ingredients = allFoods.filter(function(food){    
  			return food.type != sortedType; // 
		});  


3. Now console log the resulting array, `ingredients` on a line below your other code.

		// your code should look like this
		var sortedType = 'meat';
		var ingredients = allFoods.filter(function(food){    
  			return food.type != sortedType; // 
		});  
		console.log(ingredients);

The array `ingredients` should contain only the food items that don't have the property `type:'meat'`. 

		// ingredients
		[ {food:'apple', type:'fruit', flavor:'sweet', color:'red'},  
	    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'rice', type:'starch', flavor:'savory', color:'white'},  
	    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
	    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'potato', type:'starch', flavor:'savory', color:'white'}  ]

Now we have a list of all of our foods that we can use in our meat free recipe. Let's keep building this Recipe!

Click next to get cooking!

---

## Recipe Generator: Tweaking the Flavor

We are on our way! We have a nice list of Ingredients to work with but we need to narrow things down a little bit and make sure it tastes good.

We want to keep the flavor complex but not overly sweet. Perhaps we should remove at least one sweet thing from our `ingredients` array in order to keep the the recipe flavor balanced.

Sounds like a plan! And as it turns out there are a few built-in methods that would help us here!

We can use the [`.findIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex) method to return the index of the first element in our array that satisfies a test we provide. And then once we have the value of the index we can use the [`.splice()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) method to remove that item from our `ingredients` array.


Here's how we can use `.findIndex()`:

	//find the index of pasta
	var dinner = ['pizza', 'pasta', 'salad', 'dessert'];
	var pastaIndex = dinner.findIndex(function (food) {
	  food ==  ‘pasta‘
	});
	// index of 2nd element in the Array is returned,
	// so this will result in '1'

In the above example the array `dinner` represents a meal. But we've decided that there is too much food and we want to remove `pasta` from the list. In order to find the index of `pasta` we use `.findIndex()` to test which elements in the array are equal too the string 'pasta'.

Cool. Now that we can use the `.splice()` method to remove the the element based on the index we just found. 

`.splice()` allows use to both remove and add items to our array. For now, we are only using it to remove items so we need to provide two parameters in order to use this method, `start` and `deleteCount`. 

The `start` parameter represents the index at which to start changing the array, in our case this is represented by the variable `pastaIndex`. `deleteCount` indicates the number of array elements that will be removed, in our case only 1 item should be removed. The basic sytax looks like this: `array.splice(start, deleteCount)`

Here is how we can use `.splice()` to remove `pasta` from our `dinner` array:

	// remove 1 item at index position represented by the variable pastaIndex
	dinner.splice(pastaIndex, 1); 

Our full code would look like this:


	var dinner = ['pizza', 'pasta', 'salad', 'dessert'];
	// step 1: find the index that is equal to 'pasta' and assign it to the variable pastaIndex
	var pastaIndex = dinner.findIndex(function (food) { 
	  food ==  ‘pasta ‘
	});
	// step 2: remove 1 item at index position represents by the variable pastaIndex
	dinner.splice(pastaIndex, 1); // dinner is now ['pizza', 'salad', 'dessert']


That seems pretty useful. Let's see how this might help us with our recipe planning!

##### `.findIndex()` and `.splice()` Exercise

We have decied we want to remove a 'sweet' item from `ingredients`. So let’s start by using `.findIndex()` to locate the first sweet food in our array.

1. One line down from where you've created the variable `sortedType` create another variable called `sortedFlavor` and assign it the value 'sweet'. 

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';
		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		console.log(ingredients);

2. Start a new line below your current code and use `.findIndex()` to locate the first instance when an object's `flavor` is equal to our `sortedFlavor`;

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';
		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		console.log(ingredients);
		flavorIndex = ingredients.findIndex(function(food) {
		  return food.flavor == sortedFlavor;
		});

3. Awesome! Now console log the `flavorIndex` for your reference.

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';
		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		console.log(ingredients);
		flavorIndex = ingredients.findIndex(function(food) {
		  return food.flavor == sortedFlavor;
		});
		console.log(flavorIndex);

4. You're doing great.  On a new line use `.splice()` to remove the first instance of the `sortedFlavor` from `ingredients`.

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';
		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		console.log(ingredients);
		flavorIndex = ingredients.findIndex(function(food) {
		  return food.flavor == sortedFlavor;
		});
		console.log(flavorIndex);
		ingredients.splice(flavorIndex, 1); 

Alright! We did it, that sweet item has been removed!

But honestly, it still feels like our recipe has a few too many ingredients. Good thing we can use `.splice()` to quickly remove something else.

5. Create a new variable called `sortedItem` below your current code. Assign it the value `Math.floor((Math.random() * ingredients.length  - 1))`. We are doing this in order to create a random value that does not exceed to total number of `ingredients`.

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';
		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		console.log(ingredients);
		flavorIndex = ingredients.findIndex(function(food) {
		  return food.flavor == sortedFlavor;
		});
		console.log(flavorIndex);
		ingredients.splice(flavorIndex, 1); 
		var sortedItem = Math.floor((Math.random() * ingredients.length  - 1));

6. Finally, below your current code start another line and use `.splice()` and to remove a random items from the `ingredients` array, use `sortedItem` as the `start` parameter. Below that, console log `ingredients` one more time so we can see the changes.

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';
		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		console.log(ingredients);
		flavorIndex = ingredients.findIndex(function(food) {
		  return food.flavor == sortedFlavor;
		});
		console.log(flavorIndex);
		ingredients.splice(flavorIndex, 1); 
		var sortedItem = Math.floor((Math.random() * ingredients.length  - 1));
		ingredients.splice(sortedItem, 1);
		console.log(ingredients);


Amazing! We have what is shaping into a real recipe! Now we just need to add some quanities to our ingredients and we can start preparing the food!

Click next to keep building!

---

## Recipe Generator: Adding Quanities

Our recipe is almost ready! We have a good list of ingredients with a nice balance of flavors but now we need to figure out how many of each item to include in the final dish! 

We can use the [`.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) method to do just this. `.map()` (syntax: `new Map([iterable])`) first iterates through an array, second, calls a provided function on every element in that array and third, returns a new array of the results.

It looks very similar to `.forEach()` when used. Here's the basic syntax:
	
	//introducing .map()
	var nums = [10, 20, 30, 40];
	var halfs = numbers.map(function(x) {
	   return x / 2;
	});
	// halfs is now [5, 10, 15, 20]
	// nums is still [10, 20, 30, 40]

The above example shows us how to use this method to manipulate numbers. It is very useful for this but we can also use this to manipulate strings!

Let's say you had a list of ingredients for a recipes contained within in an array.

	// arrays of strings
	var ingredients = ['chicken', 'apple', 'broccoli', 'rice'];

Familiar right?

So imagine we want to print the items out into a shopping list but we also want to add quantities in front of each food item in the array. We need 2 of each item according to our recipe.  We could use the `.map()` method to manipulate the content of the food array, adding the number two in front of the the food item and pushing these results into a new array.

Our code would look like this:

	//`.map()` as used with an array of strings
	var ingredients = ['chicken', 'apple', 'broccoli', 'rice'];
	var groceryList = ingredients.map(function(ingredient) {
	   return '2 ' + ingredient;
	});
	
If we were to print our two arrays:
	
	// as such
	console.log(ingredients);
	console.log(groceryList);

We would see that `ingredients` is still `['chicken', 'apple', 'broccoli', 'rice']`.
And `groceryList` is now `['2 chicken', '2 apple', '2 broccoli', '2 rice']`.

Pretty fun stuff, right? It should come in pretty handy for assigning quanities to our ingredients.

Let's go for it!

##### `.map()` Exercise

In the editor you should see the code you have written so far:

	//your code should look like this
	allFoods = [  
    {food:'chicken', type:'meat', flavor:'savory', color:'white'},  
    {food:'apple', type:'fruit', flavor:'sweet', color:'red'},  
    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},  
    {food:'rice', type:'starch', flavor:'savory', color:'white'},  
	{food:'beef', type:'meat', flavor:'savory', color:'brown'},  
    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
    {food:'potato', type:'starch', flavor:'savory', color:'white'},  
	]

	// your code should now look like this
	var sortedType = 'starch';
	var sortedFlavor = 'sweet';

	var ingredients = allFoods.filter(function(food){    
	  return food.type != sortedType; // 
	});  
	
	flavorIndex = ingredients.findIndex(function(food) {
	  return food.flavor == sortedFlavor;
	});
	
	ingredients.splice(flavorIndex, 1); 
	var sortedItem = Math.floor((Math.random() * ingredients.length  - 1));
	ingredients.splice(sortedItem, 1);


1. Use `.map()` to create a new array, titled `recipe`, which contains the names of the foods you have left in the `ingredient` array. Use `Math.ceil((Math.random() * 2))` to add a random integer between 1-2 in front of each item before you add it to the new array.

		//your code should look like this
		allFoods = [  
	    {food:'chicken', type:'meat', flavor:'savory', color:'white'},  
	    {food:'apple', type:'fruit', flavor:'sweet', color:'red'},  
	    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'rice', type:'starch', flavor:'savory', color:'white'},  
		{food:'beef', type:'meat', flavor:'savory', color:'brown'},  
	    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
	    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'potato', type:'starch', flavor:'savory', color:'white'},  
		]

		// your code should now look like this
		var sortedType = 'starch';
		var sortedFlavor = 'sweet';

		var ingredients = allFoods.filter(function(food){    
		  return food.type != sortedType; // 
		});  
		
		flavorIndex = ingredients.findIndex(function(food) {
		  return food.flavor == sortedFlavor;
		});
		
		ingredients.splice(flavorIndex, 1); 
		var sortedItem = Math.floor((Math.random() * ingredients.length  - 1));
		ingredients.splice(sortedItem, 1);

		var recipe = ingredients.map(function(food) {
		   return Math.ceil((Math.random() * 2)) + " " + food.food ;
		});

3. Awesome! Now let's console.log our ew arrays. Write the console log on a new line below your existing code.

		// your console log should look liek this
		console.log(recipe);

We can see that `recipes` contains a list of our ingredients, each with a quanity defined. You did that! Well done!

This looks like a recipe folks! I bet it'll taste delicious

Click next to format the recipe and wrap things up!

---

## Recipe Generator: Wrapping it Up

Ok so now we have a Recipe Generator! Well done!

It's pretty nifty. It can combine lists of foods, filter out particular types of ingredients, and modify the flavors of the resulting recipe.

The final code should be in you editor and it should look something like this:

	//provided array
	var guestFoods = [  
	    {food:'chicken', type:'meat', flavor:'savory', color:'white'},  
	    {food:'apple', type:'fruit', flavor:'sweet', color:'red'},  
	    {food:'broccoli', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'rice', type:'starch', flavor:'savory', color:'white'},  
	]

	//user array (they make this)
	var myFoods = [  
	    {food:'beef', type:'meat', flavor:'savory', color:'brown'},  
	    {food:'pear', type:'fruit', flavor:'sweet', color:'green'},  
	    {food:'kale', type:'vegetable', flavor:'savory', color:'green'},  
	    {food:'potato', type:'starch', flavor:'savory', color:'white'},  
	]

	//using .concat() to combine your array with the provided array, creating a new array
	var allFoods = guestFoods.concat(myFoods);  
	console.log(allFoods);
	
	var sortedType = 'meat'; // representing the type we wish to remove
	var sortedFlavor = 'sweet'; // representing the flavor we wish to cut back on

	// using .filter() to create a new array of all foods that do not equal the sortedType
	var ingredients = allFoods.filter(function(food){    
	  return food.type != sortedType; // 
	});  
	
	// using .findIndex() to locate the first instance of the sortedFlavor in ingredients
	flavorIndex = ingredients.findIndex(function(food) {
	  return food.flavor == sortedFlavor;
	});

	// using .splice() to remove the first instance of the sortedFlavor from ingredients
	ingredients.splice(flavorIndex, 1); 

	// using .splice() to remove another random ingredient
	var sortedItem = Math.floor((Math.random() * ingredients.length  - 1));
	ingredients.splice(sortedItem, 1);

	// using .map() to add qauntites
	var recipe = ingredients.map(function(food) {
	   return Math.ceil((Math.random() * 2)) + " " + food.food ;
	});

	console.log(recipe); // console logging the final recipe

At the moment our recipe generator is designing a dish that doesn't include meat and isn't too sweet.  However if we change the `sortedType` and `sortedFlavor` variables we can change the type of dish that we are creating.

Go ahead and give it a try. Change `sortedType` and `sortedFlavor` to 'fruit' and `savory`. Apply your changes and see what happens!

Your recipe changed pretty dramatically didn't it.  You could keep doing, coming up with a new recipe each time. Your party is gonna be full of some amazing orginal recipes and dishes! Great job!

You made this awesome Recipe Generator all while learning about built-in methods to iterate through an array. 

--- 

## Review Built-In Method for Arrays

Let's take one more look at the built-in methods we just learned:

+ `.forEach()` is a method that we can use to iterate through an array in place of a for loop.
+ `.concat()` is used to merge two or more arrays and return a new array. 
+ `.filter()` creates a new array with all elements from the current array that pass a test carried out by a callback function.
+ `.findIndex()` returns the index of the first element in our array that satisfies a test we provide.
+ `.splice()` allows use to both remove items from our array.
+ `.map()` iterates through an array, calls a provided function on every element in that array and returns a new array of the results. 

And the most fun thing is there are even more for you to use and learn! But for now let's take a moment to just celebrate.

You should feel really pleased with yourself!

















