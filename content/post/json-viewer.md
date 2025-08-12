--- 
title: thinking about json differently
date: '2025-05-31'
tags: 
    - coding
description: Tables vs structured data - can json be for everyone?
---

Recently I had a somewhat philosophical conversation with a co-worker regarding the role of `json` outside of the web - and in fact outside of software development entirely.

> JSON - Javascript Object Notation - a structured data format that makes up a good portion of communication on the internet

e.g.

```json
{
    "latitude": 52.52,
    "longitude": 13.419998,
    "timezone": "GMT",
    "precipitation_sum": [0.00, 11.70, 0.90, 0.00, 1.70, 2.80, 0.30]
}
```

Tabular data once began its life in accounting (probably) and has become a ubiquitous part of many parts of life, whether it is in the form of spreadsheets at work, some stats in a video game or your fitness tracker's dashboard.

We pondered to ourselves why every json viewer continued to use symbols and characters to express the structure of the data. Were they trying to make reading json inaccessible to those not in the know?

Suppose excel showed commas between columns rather than nice straight lines.

For example, most online json readers will format an array as `["Apple", "Pear", "Banana"]`. Is this really the best we can do? Sure, it's probably formatted nicely so that it nests properly, but I think we can do better. Maybe something like an html list...

- Apple
- Pear
- Banana

There we go, you could walk up to anyone on the street and they would immediately know its a list. And yes, I know that for some use cases, clarity of syntax is more important - but here I want to focus on making json accessible "to the masses", rather than ensuring it can be parsed properly by a machine. I want to convey the structure of the data as simply and cleaning as possible.

After lists, there really isn't that much left, the remaining structural component is key-value pairs, which, while there are many ways to display these, the simplest and existing option might be something like `key: value`. This isn't just a json thing, but an english language thing, going back as far as the 1600s the colon has been used to expressed an introduction, a way to expand on something.

> "Colons can introduce many things: descriptors, quotes, lists, and more."

While the meaning isn't exactly that of key-value pair, you can see why json, python dictionaries, YAML and many other markup languages choose to make use of the colon. So for now, perhaps lets stick with that.

Doing this, the example in the introduction could be re-written as something like...

- latitude: 52.52
- longitude: 13.419998
- timezone: GMT
- precipitation_sum:
  - 0.00
  - 11.70
  - 0.90
  - 0.00
  - 1.70
  - 2.80
  - 0.30

Lastly, there are a few other minor bits and pieces. Firstly, as above we denoted levels of nesting using indentation, but we could also use contrast or colour to show the distinction. JSON also supports foundational data types (e.g. boolean, number, string), we could try to convey this to the user too, in json this is done with quotation marks, but we could use colour or symbols/icons.

In my mind I was also curious about how one might navigate a json object in a viewer like this - with nesting and lists, this becomes a far less space efficient data structure than a table for rendering to the screen. The unusual shape of JSON doesn't help either, unlike a table it is inconsistent and bulges out in places where it nests.

I imagined...

- Navigating by depth
    - Showing only so many levels of nesting at a time
    - Allowing users to delve into object to discover more
- Searching
    - Jumping to specific objects where a key or value contained the query

I had fun spending a couple of afternoons cobbling together a prototype. It's far from what I imagined it could be, but it might be enough to get the idea across.

![](/img/jsonless.png)

You can give it a try over [here](https://jsonless.netlify.app/) (not made for mobile).