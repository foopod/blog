--- 
title: thinking about json differently
date: '2025-05-31'
tags: 
    - coding
description: Tables vs structured data - can json be for everyone?
---

Recently I had a somewhat philosophical conversation with a co-worker regarding the role of `json` outside of the web - and in fact outside of software development entirely.

> JSON - Javascript Object Notation - a structured data format that makes up a good portion of web requests

e.g.

```json
{
    "latitude": 52.52,
    "longitude": 13.419998,
    "timezone": "GMT",
    "precipitation_sum": [0.00, 11.70, 0.90, 0.00, 1.70, 2.80, 0.30]
}
```

Tabular data once began its life in accounting and has become a ubiquitous part of many jobs, whether it is in the form of spreadsheets, data science or simply a web dashboard for your fitness tracker. We pondered to ourselves why every json viewer continued to use symbols as expressions to convey the structure.

For example why visualise a list using `[1, 2, 3]` which you are trying to improve readability, this is a solved problem at this point.

- 1
- 2
- 3

And yes, I know that for some use cases, clarity of syntax is important - but here we are focussing on making json accessible "to the masses", to which clarity of structure is vital.

After lists, there really isn't much left of json, the remaining structural component is key-value pairs which while there are many ways to render this, the simples might be something like `key: value`. And then for example using indentation to denote levels of nesting.

In my mind I was also curious about how one might navigate a json object in a viewer like this - with nesting and lists, this becomes a far less space efficient data structure than a table for rendering to the screen.

I imagined...

- Navigating by depth
    - Showing only so many levels of nesting at a time
    - Allowing users to delve into object to discover more
- Searching
    - Jumping to specific objects where a key or value contained the query

So I cobbled together a prototype...

![](/img/jsonless.png)

Give it a try over [here](https://jsonless.netlify.app/), I would be curious to see what you think.