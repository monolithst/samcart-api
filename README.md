# Easy, Quick and "It just Works"
Its 2022, and programming the internet just got easier.
If you read further you'll find out how to "just make it happen".

## The Story
I get it, you were just accepted into the beta program for SamCart's api, and you want to integrate the api immediately. That's my story, and after one beer and a few minutes of "tap tap tap" I am in business, all typed and scripted, and ready to go.

But you don't have to worry about doing any of that "tap tap tap" to get the api up and going. Why?

## This SamCart api WORKS
I know how fast the internet moves. I promise that I can't promise anything. But I do promise that this currently works, and its very easy to update it. I don't have any testimonials, other than I just went "wooo it works!" and then wrote this README. That, in my humble opinion, should be good enough to prove it works.


### The Offer
Look this is an amazing deal.
- I do all the foundational work and provide an api that is "holy goodness" easy to maintain and maybe you help maintain it from time to time. At least if it breaks...
- I provide this free of charge (because its GPLv3), maybe you'll decide other people's freedom is just as valuable as your own and not try to lock others out.
- You just do a simple "npm install samcart-api", and you say "Hey, this Mike guy is pretty cool"


## Do We have a deal?
If so, just follow along with the instructions... I promise, it'll be painfree. 

## Installation instructions

```
npm install samcart-api
```

That's it!

## How To use it.

I am not going to go into full depth of SamCart's api. It is available on their website. 
[Click Here](http://developer.samcart.com/)

Overall this is how it works
- You create a new Configuration() object using your apiKey.
- You create an instance of the part of the api that you want to use, passing in your new handy dandy configuration.
- You call the functions that are available on that api.

That's it.


Example (non es6)
```
const { Configuration, ProductsApi } = require('samcart-api')

const configuration = new Configuration({ apiKey: "insert-your-api-key-here"})
const productsApi = new ProductsApi(configuration)
await productsApi.getProducts()
    .then(axiosResponse => {
      return axiosResponse.data
    })
    .then(console.log)
```

This example prints off all of the products in your account. Cool right!

Example ES6
```
import { Configuration, ProductsApi } from 'samcart-api'

const configuration = new Configuration({ apiKey: "insert-your-api-key-here"})
const productsApi = new ProductsApi(configuration)
await productsApi.getProducts()
    .then(axiosResponse => {
      return axiosResponse.data
    })
    .then(console.log)
```

Everything works the same, except that its ES6 syntax.


## Building from scratch
So I have what should be every command to generate this Api from scratch. If you do...

```
npm run build
```

It will pull down the latest api spec, generate bindings, and then put them in the dist folder for javascript and typescript users alike. 

If you do...

```
npm run dist
```

It'll do everything the build does, plus push it to npm.

## For the future...
You may be shocked by the devDependencies. These are provided (free of charge), for the motivator who is interested in creating unit tests and BDD tests to ensure that the api works as expected... (or proving samcart changed everything up and wrecked everyone). I like these tools, I use them. Maybe you might too.
