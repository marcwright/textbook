# Ape-y Eyes, W05D04

## Objectives
- Give an example of a useful API
- Build an API that performs CRUD functions
- Import and make human-readable information from another API
- Convert data to and from valid JSON

APIs give you a way of running code on someone else's server. They have total control over what code you're allowed to run — you can't just assume you can run `.sample` or something on whatever they give you.

Taking a look at the API you used, here's it's documentation:

http://version1.api.memegenerator.net/#Generators_Select_ByTrending

It tells you exactly what it does:
```
Returns recently trending generators.
```

That's it. You can't specify how many meme generators you want it to return, or which meme it returns, nothing. If you **could**, it would let you add parameters to your request. Adding parameters to a request is just like adding arguments to a method. This API is like a method that doesn't take any arguments.

I think the API you **wanted** is this one:

http://version1.api.memegenerator.net/#Instance_Create

It tells you exactly what it does:
```
Creates a captioned image.
```

Notice that this one lets you set a couple different parameters, including `username`, `password`, `generatorID`, `imageID`, `text0`, and `text1`. Here's a sample URL that uses all those parameters (I signed up for a MemeGenerator account):

```
http://version1.api.memegenerator.net/Instance_Create?username=robertakarobin&password=wdiiscool&generatorID=45&imageID=20&text0=robin&text1=is%20cool
```

This page I liked to before tells you exactly what each of those parameters does:

http://version1.api.memegenerator.net/#Instance_Create

When you make a GET request to that URL, MemeGenerator runs some code to make a new image for you. Again, the only "arguments" you can specify to affect what it does are the URL parameters it lets you use. When it's done running its code, it sends you back a string of information:

```
{"success":true,"result":{"generatorID":45,"displayName":"Insanity Wolf","urlName":"Insanity-Wolf","totalVotesScore":0,"imageUrl":"http://cdn.meme.am/images/400x/20.jpg","instanceID":61374133,"text0":"robin","text1":"is cool","instanceImageUrl":"http://cdn.meme.am/instances/400x/61374133.jpg","instanceUrl":"http://memegenerator.net/instance/61374133"}}
```

So now you have the URL for an image you can use on your site:

http://cdn.meme.am/instances/400x/61374133.jpg

The power of this is that you can change the URL parameters you're sending based on the input a user gives you. So if a user says they want their top text to be "Hello" and bottom text to be "World", you could do something like:

```
@image_source = HTTParty.get("http://version1.api.memegenerator.net/Instance_Create?username=robertakarobin&password=wdiiscool&generatorID=45&imageID=20&text0=#{params[:top_text]}&text1=#{params[:bottom_text]}").parsed_response["instanceImageUrl"]
```
