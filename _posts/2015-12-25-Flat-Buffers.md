---
title: FlatBuffers
layout: post
img: /img/flatbuffers.jpg
---

In this post I'm going to talk about a new serialization library I started using recently. Flatbuffers although less flexible
than protobufs, provide a huge performance boost and was exactly what I needed to reduce memory usage for my application. My 
experience with flatbuffers involves building the buffer in Python and reading it out in Go. The performance advantages and
disadvantages may differ for other languages.


### How to use Flatbuffers?
1. You define a schema for your datastructure you want to serialize.	

2. Use a flatc compiler to generate helper classes or functions to encode and decode the data. 

3. Use a builder object to create a flat binary buffer. 

4. When reading it back, you obtain a pointer to the root object and then use helper functions to access fields.


## Advantages of using Flatbuffers

1. Super fast to encode and decode.

2. No heap allocations while encoding and decoding, making it very efficient. 

## Disadvantages of using Flatbuffers

1. Less flexible than protobufs and some other serialization libraries. For example, once the buffer is built
   you can not add new fields to the buffer or change any fields.

2. Building a flat buffer is more complicated than creating a protobuf object. It must be created bottom up and
   can be a bit complex when you have nested objects and strings involved.

3. Takes up more space on the wire. 


## Conclusion
If your project involves alot of encoding and decoding where memory is a huge concern then I highly recommend
trying Flatbuffers. I'll be adding another post which will be a detailed tutorial on how to use flatbuffers but 
for now there is already great information out there if you want to learn.

Below is a list of some tutorials and documentation that really helped me understand and use flatbuffers:

* Robert Winslow's tutorial and benchmark: `https://rwinslow.com/posts/use-flatbuffers-in-golang/`

* Googles github page on flatbuffers: `https://google.github.io/flatbuffers/md__go_usage.html`

* Flatbuffers github page: `https://github.com/google/flatbuffers`