# Godwin - the AI that teaches 

This is a public demo repo for Godwin! This is just the random name I chose for this project. Godwin teaches concepts, ideas, classes, and anything you want to you, learning the teaching style
that's best for you over time, connecting to research that you want to get into or classes that students are in, and legitimately trying to express the intuition of difficult ideas without coating
it in intellection or adding complexity. This has been such a fun challenge to build; I'm eager to release it soon, as a few friends are asking to actually use it!

The demo below focuses on "show visuals fast", but my favorite parts with this AI tool are actually completely simple, almost 2-dimensional visuals. Imagine a human being at a whiteboard; I learned
a counterintuitive truth around doing this project. As the quality of visuals evolved, I learned a type of dimensional collapse was present in learning: sometimes, circles and arrows and squares are all you need :) 

** Turn sound on**

https://github.com/user-attachments/assets/76f98f57-af1f-40f1-a641-8023604421fa

# Technologies

This is a full tech stack that turned into an enormous task. The front-end is just React, Vite, etc. I use 3 to 4 websockets for the entire agentic voice flow, and there are some more latency minimizers and speedups
that I can add in the near future. I played with countless VAD engines, turn detection mechanisms (server-side, CPU inference, getting creative, lol!) before finding the right technology to use that simply worked. 
I use Firebase Realtime Database because it's just my favorite and go-to for stuff: I always pair it with real-time listeners to just update. Let's get to the fun stuff!

# Inference and the 'Fast Reply'

You can only hear it around 65% of the time here, but this AI can actually reply faster than (I think, in my humble opinion) almost any other tool that exists currently. I tried a crazy idea (using MiniLM, a websocket,
creating training data from scratch (a long story! Lol), creating a classifier, etc. I wanted something that could beat OpenAI or Anthropic or any other voice agent in terms of raw, natural feel - it needed to reply *right away*, the instant you were done talking. Things that I learned (even though the code is closed-source for now, I can share learning!). 

1. Really fast inference providers can have database hops that add latency to websocket connections. This was the funniest thing to realize: that a $5 railway server was faster than a $20+ faster inference provider, lol!
2. I can run CPU inference with really clever ONNX runtimes and get creative. This was my first time actually approaching an open-ended problem no one had really approached before, and trying things in ML until I got it to work
3. Fast inference providers (Cerebras is really fast!) can allow for fast code, but the actual time to reply is something else altogether. This is where the real engineering began, and I'm really excited for what's to come! There's still room for creative, independent builders to build epic stuff that large companies can struggle with.
4. (Crazy take) Training models that can listen and reply at the same time *actually isn't that hard*. I'm sure these will actually come soon!

# Tech Stack
xAI for TTS, STT, Railway for a bunch of websockets (I switched from EC2, AWS, and tried a bunch of stuff). I tried many inference providers and models including Bedrock, etc, but I really liked the pure fast times of Cerebras. Vite and Three handle visuals with a custom designed pipeline! Then, the RAG is the secret sauce for me. That's why it's closed source, lol!  I created data for something with MiniLM, and also tried fine-tuning, but found that models are getting really good really fast. 

# Future Work/Collaboration
The core models/engine are closed source for now and in-progress. I think I'll release this for folks to try out as I add a few other thins. If you're interest in this or curious for early access, or want to give me criticism/feedback, please reach out to me! adengitstuff@gmail.com
