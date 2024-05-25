## The Future of AI and Generative Models in Hardware Development
I think in 10 or 20 years, we'll actually start to have things that can truly be agentic, where they can formulate hypotheses, create actions, execute actions, observe consequences, update hypothesis generation. Yeah, we're going to, is it going to take 100 MW to do it? Maybe so it's not 20 W of energy like your brain, but that's progress. I'm actually super excited and pumped about this. Like I see this is like when I'm 80 years old and looking back, we will have really, really made a dent and made this, but I completely have changed the world. Hi, this is Derek Harris and you're listening to the A 16 Z AI podcast where we dig into all things artificial intelligence with our in house team of experts as well as the founders, engineers, and researchers working at the state of the art case in point for our first interview style episode on the new feed, a 16 Z partner Matt Bornstein and I speak with Naveen Rao, who's currently vice president of Generative AI at Databricks navina is particularly knowledgeable about the space, having spent years building AI chips, first at Qualcomm and then as founder of AI startup Nirvana Systems back in 2014 Intel acquired Nirvana in 2016 after a stint at Intel Rao reemerged with Mosaic ML in 2021, this time he focused on the software side of things, helping customers train their own MP and also fine tune Foundation models on top of an optimized tech stack Databricks acquired Mosaic in July 2023.

This discussion covers a gamut of generative AI topics, although we focus on how the enterprise flair market is shaping up. Navene Nelson shares his thoughts on what he prefers finally being part of the technology and crowd, even if it means he can't escape talking about AI outside of work. Because we recorded this on the heels of the Nvidia GTC event, we kick off the conversation talking about Nvidia's continued dominance in running AI workloads. Nvidia has also been really on top of each trend, so kudos to them for doing that really well. They've been able to see the trend, for whatever thing it is, low precision tensor cores, what have you, and execute extremely well. So it's just a formidable competitor for anyone to go up against. Everyone talks about the sort of CUDA lock-in and that sort of thing.

I actually don't think that's the reason anymore. I think it's just they've become the gold standard and it introduces risk to move to any other hardware platform. We're always looking at new hardware to see if we can find a better TCO. Basically like effective flops per dollar is with a number I look at and it's hard because they do build a good part. And you know, we can extract a lot out with the mature software stack that exists. That's really what keeps it locked in, is just the maturity. When you say you look at other hardware platforms, are you at liberty to divulge what those are. And my brain immediately goes to what the cloud platforms are building. Obviously, there are some startups experimenting in the space, but I'm curious what you're looking at. We, I mean, we talked to all of all of the above, but to this at this point in time, it's still very hard to move away from Nvidia because if we're trying to go build models to for some purpose, that represents the shortest path to the to the goal, if you will. Anything else introduces some friction at this point. Now, I think by the end of the year that might actually change.

## Transformer Architecture Impact on Chip Companies and Hardware Optimization Challenges
There might be some other players that are capable of getting to the end goal without so much friction. We're building our software stack to make that really easy for our customers, delivering the best TCO through a stack they already know how to use. Many are building on top of the Mosaics Mosaic data brick stack. Abstracting away hardware details can provide customers with more choice. Language models have mostly standardized around the transformer architecture, creating an opportunity for chip companies to tailor products to a more uniform set of workloads. This shift has reduced the need to support various neural network families like common nets, RNNs, LSTMs, and others.

So it was actually quite a bit more difficult to actually launch some piece of hardware because you had to have enablement for all these different things that do optimization for all these different things. Now, as you said, it's kind of a transformer, or a diffusion model. I would say diffusion models are still pretty important workloads. So those, those two things have a pretty confined set of primitives. And so you can just go optimize it. Now, is it good? I'm not really sure what good means. I don't think it's the be all end all. I think there are some problems with transformers that are still not quite addressed, whatever the next thing is is going to be built off of the learnings from transformers. So I mean, whose nations grounding are still problems? And are they solvable within the confines of a transformer architecture? I'm not entirely sure. I think there's going to have to be some modification here. I mean, we're doing things like Rag, which I'm sure you've heard of for people augment generation. And this is basically, it's a way you can almost think of this as extending the context window to a whole bunch of other documents using approximate search.

## Evolution of Neural Networks and Hardware Adaptation
I think it's a pattern that works and adds value today due to approximate search and embedding models. Can we integrate this more into the neural network paradigm from the start to align better with truth? The transformer as a standard paradigm benefits hardware vendors, allowing them to enter the game, leading to increased competition this year. While the industry may be overly focused on this architecture currently, progress often involves modifying existing paradigms for advancement.

And since you're one of the few people who really is an expert on both the hardware and the software side, can you just give us some intuition for why building custom chips was so hard when you had to support, say, CNN and Nr and, you know, like many different architectures and kind of looking forward like how hard will it be for the chip industry to retool if we do move off Transformers? One part of it is that fundamental concept in hardware is constraining the number of computational motifs motif, meaning like a set of operations that occur over and over again. So if I do a matrix multiplication times a, you know, a linear scaling term with a lookup table after like if you see that same thing happen over and over again, now I can build a piece of hardware that optimizes that. So building custom hardware has always been about finding those dominant motifs and patterns, and then basically building something very bespoke for it. So there's an inherent trade off between that and flexibility. Cpu's, we're kind of the dominant paradigm for a long time because we care very much about the sequential blasting of instructions.

## Software and Hardware Evolution for Data Parallelism and Model Development
That's what most applications like Microsoft Word or whatever care about. Now we went to this world where it's very data parallel and having that right amount of flexibility to enable the next generation of algorithms like Transformer, while also having good enough performance on certain primitives is really has been the trade off. And when we've started to build software, hardware in like in Nirvana, for instance, you know, we were very focused on a particular set of primitives like multi wire perceptrons and convolutional nets, But then we had things like res nets, which are convolutional nets, but have a different sort of flow of information that presented some issues. We change the way we potentially will do convolutions. Can we do them in the frequency domain instead of a time domain that actually changes the motifs? Again, a lot of that kind of worked in favor of something like a GPU that was a little bit more flexible, but now that we have something that's more stereotypes like with the with the transformer, it gives us an opportunity to go build something a little bit less flexible, but more performant. You can think of it as at its very limit.

## Market Trends in Training Bespoke AI Models and Custom Chip Development
Imagine taking a fully trained neural network and burning it into silicon to find optimizations. Zeros in the network can be eliminated, reducing the need for transistors. However, the question arises whether the market demand justifies the cost of developing such specialized hardware.

You mentioned the market size for this is the market the current players or and maybe a few others training foundation models are training these large models or is this something where you know, enterprises are realistic that going to invest in like these very prescribed and inflexible chips? There might be a market for both, to be completely honest with you. So training models and building bespoke models for different domains is it's just going to be a thing. It is a thing right now and there's a lot of reasons for it. 1 if you're a regulated industry, you know, you want control. Also, companies want differentiation. They want to make models that are specific to their data, to their customers. And you know, they can have something that is differentiated from their competitors. But at the same time, they're there some dominant use cases like say ChatGPT GPT-4 has changed a bunch over the last year. So I know people like to say, oh, it's a one year old model. It's like, well, it's not really, it's always changing out of the hood. Let's say just take for instance, and maybe it is a one year old model, or maybe that one year old model is still useful.

If I can run enough inferences through this or have 100 million subscribers paying 20 dollars a month, it starts to justify the 30 million bucks upfront cost of building a chip of this complexity. Each chip would be cheaper to run each inference, making it worth it. Hardware is no longer the big, expensive, immutable thing it used to be. Building a new chip every six months for 30 million bucks is feasible now. By considering the time to live for a model and the user base, a financial model can justify building new chips for different purposes. The transformation in the industry is happening rapidly.

## Custom Training Models and Feedback Loop for Model Performance Enhancement
A few years ago, Google was one of the few companies doing this, but now there are newer companies entering the field. Let's shift focus from hardware to software. It seems you prefer custom training models. What are the tradeoffs and ideal use cases for each approach? There isn't a single answer. We aim to support customers based on their needs and value. Currently, most of our business involves custom training, with an expected increase in inference usage once in production. I see it as a balance between fine-tuning and pre-training, which I consider all part of the training process. Inference is simply the deployment phase. I predict a near 50-50 split in terms of financial investment between training and inference, as training leads to production.

When something is put into production, feedback is gathered to improve training. These processes work together synergistically. Models are not permanent but snapshots in time, typically lasting about six months. Even advanced models like GPT-4 require modifications after this period. Continual training and improvement are essential for models in production.

## Trends in Training and Inference Scaling and Continuous Model Development Cycles
We don't prioritize trends, but it appears that training and inference grow simultaneously. This shift is notable as applications now have a shorter lifespan, impacting how companies operate. Unlike chips lasting two years, some models are maintained longer, especially in cars where chips endure rigorous testing for over a decade.

But in a data center, things move much faster because we have these upgrade cycles. And I think in the same way, we're going to see models, kind of the ones that are at the forefront that are, you know, you're getting feedback against all the time, you're going to be updating a lot more. And when I say six months time to live, I don't mean that you're going to throw it away and build something completely different. After that, you're, you're basically going to continue to support your application better. That's one of the things we've built inside Databricks is the ability to gather feedback from a model that's in deployment, Use that feedback. Then to improve the model, you actually can create supervised fine tuning data sets from it, and then fine tune the model, put a new model into a into deployment. It's kind of a continuous development cycle, sort of a thing. We see this in software all the time. It's not necessarily that you've changed your entire architecture of your application. It's that you are in continuous development. You see feedback, you get bug reports, you see performance issues, you feed those back, you see I CD them and you deploy updates.

## Democratization of Advanced Models and Infrastructure Teams in Enterprises
And so I think in the data center, we're going to see this with with models quite often people are going to be versioning moving to the next thing over. What is the difference then between doing this inside of a company like Google or OpenAI or any of the usual suspects here and actually doing it inside of your standard enterprise? Because I think what I keep hearing is this is the year we're gonna see like LLM is actually happening inside enterprises. And I'm curious what that looks because we've been told for years, it's like, this is not for everyone. This is for the experts. But now it seems like actually it's becoming kind of for everyone. So. Yeah, that's that was a large part of what we did at Mosaic. And now Databricks is making it possible for everyone to do this. So when one of our famous use cases is a company replete, has a distributed IDE, two guys built a state of the art coding model on our platform. Two guys who knew what they're doing, they're very good. But two people basically did this with our tools. So that wasn't something you could do inside of Google, you know, 5, 6 years ago.

So companies like Google and OpenAI, they built huge teams that go and build the infrastructure, make the infrastructure work, deal with failures, all that stuff. We basically taken that pattern and built it for everybody. And so we made a set of tools that make it easy to wrangle infrastructure. What we're seeing, I mean, we're seeing lots of enterprises train models. I could check the latest, but we're, we're over 100000 loms trained. It's not that it's coming, it's there. You know, enterprises are building their own models and because they have the tools now that make it tractable for them and the costs have gotten to a point where it's not like $100 million, they can, they can do something really meaningful for under a million dollars. And so I think that those those two things coming together actually made it quite important. What does that look like? Well, you know, I think a lot of enterprises are figuring this out. A lot of stuff sits under the CIO many times, you know, it's an it kind of a thing who does the infrastructure, but then there's some kind of line of business data scientist or ML engineer who's wrangling data and is the one that uses the tools.

## ML Teams and Tools for Customizing Models in Emerging Data Platforms
That's a slightly different paradigm than what people were used before with data platforms. That all sits under the CIO generally. So we have a slightly different, a slight deviation from that within companies. So typically you'll see an ML team spun up somewhere where it's close to the business and it matters. And those folks are the ones that are like, I need these tools because I need to go build this model. I need to customize this model. I know exactly what I want to do. They're smart folks. Now, everywhere, we're seeing undergrads who come out of schools like Stanford or Berkeley or whatever, who understand a lot about and LM and how to tune in and make it do what they want. They know what I Ft S FTR, oh, they know all this stuff now, at least, at least conceptually. So I think the talent is getting to a point where it's proliferating into many enterprises. It's just you're not going to see the density. You're not going to see 100 person in for a team in these, in these lines of business. You're going to see a five person in for a team. So they need tools, that abstract stuff, and that's who we sell to.

## Specialized Small Models vs. GPT-4 and Success in Specific Domains
A small model can outperform GPT-4 by being specialized in a particular domain, unlike GPT-4 which is a generalist. GPT-4 has vast data and capabilities, but for specific tasks, a focused model can excel. Specialized models, like one excelling in customer support, may surpass GPT-4 in their designated area.

It's not going to be good at doing math. It's not going to be good at Sat problems, it's just not built for that, it's built for customer support and it knows the products, but that's what the enterprise cares about. And you can kind of look at it like the cost of training or sorry, the cost of serving this very large model for a specific use case is complete and utter overkill. And everyone's seeing that now is like, I can build something that's one 100th the cost to serve, that's 100th the size, but it does my domain just fine. So why would I use this thing that costs way more? That's kind of the calculation that's happening. Do you have some examples you can share? Because I think folks would be just really interested, like this is a common claim people make, right? It's almost become accepted wisdom that if you train a small model or fine tune a small model, you can beat GPT-4. But then, then like when you actually go looking for examples, they're harder to find than you might think. I mean, the replete one is a, is a great example. That's a code completion and it's because they had dataset from their own customers. So keep that in mind, right?

It's not just a smaller model that's trained on domain specific stuff. It's also very high quality data that went into that model that, you know, OpenAI just didn't have that. That's not their domain. So Replete has a ton of data from where their customers try to use a tool like this, asks for a code completion, and they have all that data logged. They use that to train the model. So the model gets good. Actually, internally, we have a coding model as well that we use for a coding assistant. It's actually exactly the same story, made the model much higher performing than GPT-4. We don't force anyone internally, by the way, so we have, we're an enterprise company. We build tools, and we don't force any of those companies, any of those groups to use our models over GPT-4. We use OpenAI, we use all those, all the tools out there, everybody who builds an application inside of Databricks for our customers should use the best possible thing. And so we look at it like, well, if they don't flip over, that's that's proof positive that they couldn't get better performance out of a different model. But if they do flip over, then they could.

## Shift from Supervised to Unsupervised Learning and Pretrained Models
And we actually see a number of use cases internally on code generation, on assistant type stuff that is that is flipping over. We're starting to do demos now using our own models because again, we understand that domain, we understand the customer's usage, and we have data sets that characterize it. And now we can go find to the model and make it really good. One of the really big trends we've seen at andreesen Horowitz is a change from the supervised learning to unsupervised learning era. You know, we've been investing in AI companies for 8 years, call it, you know, and even longer than that. But I think one of the big takeaways from the supervised learning era, at least for us, was that it was really hard to convince customers. These big companies, like you said, to staff up a team of 2050, 100, you know, at the time we're called machine learning experts or machine learning engineers collect all this data, label it, you know, feed it through a custom training job, figure out what model architecture, right?

It was really complicated, really expensive, and really hard to get right to do machine learning on your own versus now in the unsupervised learning era with these large pretrained models, that's not really necessary. People can just take the model off the shelf and do something amazing, create a great demo. Yet you're sort of making this compelling point that fine-tuning your own model or even training your own model from scratch can do even better. It almost sounds like we're edging back towards supervised learning a little bit. Has pretrained models broken through the noise and convinced people this is important? Is some form of supervised learning or direct training on proprietary data the real answer? Maybe we found a happy medium or something like that. I'm going to slightly correct some of your terminology. This is not unsupervised, this is self-supervised, it's aggressively trained.

So the supervision comes from the intrinsic ordering of words. Once you move to auto regression, you don't need to have a labeling, the labeling is intrinsic in the data, which is pretty cool. And just to maybe explain what you're saying, you're sort of saying when we have these very long sequences of text that we're training on, the quote supervision or the quote labeling comes from the fact that a human once wrote this and their sort of structure built into it and that particular sequence of words kind of has supervision already built in. Correct? Exactly, So intrinsically, the words are ordered in a way that has meaning and I think understanding what that meaning is and how that meaning was derived is kind of what these models can do, which is pretty cool, but I think it's more than happy medium argument that you're making what we've, what we're finding now is that you still, I mean, every one of these ul is trained with supervised learning, so supervised fine tuning has to happen. You can't just pre train a model and put it in a while, it'll be, it'll go off the rails and do weird things right away.

## Self-Supervised Learning and Continuous Model Improvement
So you know, I think that was some of the early attempts if you remember, I think, what was it called? Tay from Microsoft. And you know, Galactica like these were just sort of wild models training without much fine tuning. Afterward, you get some weird behavior and so you can't really do that. Any one of them actually goes through the phase of pre-training where you get the inherent structure of language and then you start to actually, say, well, these are the patterns of input output that I want. Like somebody asked this kind of question, format it this way. These are things that are inherently bad, don't do this, you know, so that's where the supervision comes. And those supervised data sets have gotten pretty big. I mean, they're not nearly as big as pre-training, but they are getting pretty big. And so actually making a really great model is much more about the supervised part. So now we've done really well is we've we've mixed the autoregressive self supervised part along with a paradigm that does different kinds of supervision.

And that supervision can even be small, it can be 100 examples, but if you, if you train it the right way and construct the loss the right way, you can actually get profound changes to the behavior of the model that are built upon that self supervised learning. So that's the paradigm that shifted in my mind. So it's you're exactly right in that pure supervised learning required you to go and build a very high quality dataset that was completely supervised and that was hard and expensive. And you know, you had to do a bunch of ML engineering. And so that didn't quite take off. It's just, it's just too hard. But now we can get this sort of smooth gradation of performance where I say, well, I have this base model that's pretty good, understands language, understands concepts, then I can start to layer in the things that I do know. And the more I know, I know I can put in. And if I don't have a ton of information, that's okay. I can still get to something which is useful. I can put it out in the wild or in some constrained wild, get feedback, and then make that model better. So that paradigm is actually the killer paradigm.

## Readiness for Technological Projects and Data Utilization Trends
Every technology leader at every enterprise on Earth right now is probably thinking about starting a project like this, and rightfully so. This is probably the most important technology change we've seen in 10 years, 20, or even longer. To determine if one is in the right position for such a project, it is essential to have a problem, a good dataset, and seek advice from experts like Databricks. Dataset availability is usually not an issue, as most companies already possess data that can be utilized with minimal formatting adjustments, such as call center transcripts providing examples of desired behavior.

I think what's really cool about the pretraining plus supervised fine tuning paradigm is that I can start with a small set of examples, demonstrate improvement, and then scale up. Many enterprises have a clean small dataset amidst years of messy data. They can fine-tune with the clean data, see improvements, and then justify investing in cleaning up and utilizing the old data for even better results. This trend emphasizes the importance of exploring and utilizing existing data.

This is like the Indiana Jones version of finding a special artifact hidden, enabling one to conquer the world with valuable data. Many digital native businesses possess valuable data sets like buyer behavior and interactions, previously underutilized until the promise of AI materialized. Data archaeology has become challenging due to data accumulation over 20 years, stored in various formats and locations, including forgotten tape drives.

## Probabilistic Applications and Evaluation Metrics in ML
That's totally happening now because I can take that data and do something with it, which differentiates me from my competitors. Building something useful is accurate, maybe even probabilistic. Enterprises are adjusting to the idea that these applications are not deterministic. In regulated industries, deterministic models are preferred, where inputs and outputs are predictable. Generative models are more easily identifiable.

It generates new stuff, it does new mashups, and it's somewhat unpredictable. The best way to characterize this for companies is to figure out what is good and bad for your business by coming up with evaluation metrics. In academic and industry settings, various evaluation metrics like NML U and Hell swag are used to compare models for different tasks. However, for very specific or domain-specific issues, there is a lack of standardized evaluation methods. Many businesses rely on subjective judgments to determine if a person is suitable for certain roles, such as customer-facing positions. Despite this, there is a need for a reliable examination process to ensure a person's competence.

So I think that's the hard part right now, especially for regulated industries is coming up with that exam, that evaluation criteria such that it gives them signal, okay, once I run a model through, I can compare the relative merits of this model to that model on my domain. And so a lot of what we're doing now is advising companies to do that, come up with your success criteria, write it down, and then we'll start to construct an eval for you. Yeah, I was going to say customer service seems easy because it's so poor to begin with. Like an improvement is an improvement. But on the other hand, I think someone just engineered an airline or an airline chat bot to sell them a ticket for like a dollar or something. You alluded to this. I wanted to ask like you wrote a blog post a while back about thinking of Ulster like a, like a, like a kind of like a, maybe a relational database or like it's some sort of structured, you know, representation of a company's DNA for lack of a better term. And all the data they've they've been asking me, but can you elaborate on that concept? Because it does seem like to your point.

## Knowledge Base Building and Customized Reasoning in Data Analysis
We are seeing that training on decades worth of data helps in building a knowledge base on how the business works. Finding terms that people understand is a challenge to explain new capabilities beyond a database. Models can reason over new data during training or tuning, finding useful patterns. Familiarity with terms like genetics in Pubmed helps in understanding mental models of gene functions, stop codons, and promoters.

You start to understand these concepts and then when you hear new texts, you can actually say like, okay, I can find the thing that's interesting about this, this you just gave me because you have that mental model of the domain. And so this kind of customized reasoning is actually what's important. And now that term reasoning, we can start to use it a little bit. I think people are that the industry is getting a little more mature and that if I say the word reasoning, people don't like flip out. When you said that two years ago, people like, I don't know what that means. That's, I know the fine terms like, well, okay, I can, I can kind of more queerly define it in that like it's something that forms a mental model around your data. That's the customized reasoning that happens when you introduce custom data when you when you pre train or fine tune something, you start to build something that's custom reasoning engine.

I think we're moving from the database metaphor to a new metaphor, describing the same phenomenon of custom data representation for business use. Data infrastructure at the platform layer tends to remain stable for a long time. Foundational models in data infrastructure should be considered for their role in reasoning beyond data processing.

## Commitment to Foundation Models and Autonomous Domain-Specific Models
I think for the next couple of years, we're going to be in a space where we're not establishing one foundation model for a long time. This trend is similar to the early days of databases in the early 90s when companies hesitated to commit to a single database due to the constant emergence of new technologies offering faster and better solutions with unique data schemas. Large language models act as flexible schemas adapting to the data, unlike the past where specific schemas were built for different use cases, each with its own advantages and trade-offs.

So I think even back then, you would see a company probably not commit to one database for a long time. Now those patterns have become very established and I can commit to a database for a long time because it's mature. And I know that thing's going to work. It's going to be supported and it adds, it's sort of a, it's a bedrock of my business at this point. It's going to take a while for foundation models to get to that point. But I think this is actually why we start seeing this proliferation of domain specificity. And even customer specificity is like, once I build a model that understands my domain really well, you know, our vision is to have that kind of model actually start to become more agentic. It actually becomes a thing I can trust, and let's say it just is unleashed on all my data all the time. And it can go around and find interesting insights like, hey, you know what? You could actually reduce your costs on your supply chain by rejiggering this stuff.

## AI Evolution and Advancements in Business Understanding
We're not there yet, but once we have a thing that can kind of really understand my business well and have this kind of customized reasoning for my business and actually give me novel insights that I trust over and over again, then we'll start to get to this point where we have an established, mature paradigm that will live longer than six months. Naveen, you've been in this world for a long time. You've seen it from a bunch of different angles, and I've just always found you to be like an especially thoughtful person. Thank you. Can you talk a little bit from the personal side of this? Like you founded a company that was very successful, got acquired by a big company. You stayed there for a while, came out, started another, another startup. I think there are a bunch of us sort of in the AI world who have been waiting for AI to like actually work for like years. I know I count myself personally in that category. Conversely, there's a lot of new people like developing with AI for the first time, learning about AI for the first time. Like you said, kids learning in college about convolution makes me kind of sad that I'm not in college right now. You know what I mean?

## Envisioning AI Advancements and Machine Intelligence Mainstreaming
I have been in this field for a while just from a sheer interest standpoint. I spent 10 years in industry as a computer architect and software architect and then went back to get a Phd in neuroscience to bring intelligence to machines economically. Building technologies into products is crucial as it adds value to users, solves their problems, and improves their business, making them willing to pay for the product.

I've been waiting to see AI add more value and really work for a long time. We had wild ideas in the mid-2000s about building intelligent machines, and now those ideas are resurfacing. Concepts like backpropagation, convolutional nets, and transformers are converging towards a greater understanding of intelligence. It's exciting to witness machine intelligence becoming mainstream. Even discussions about extreme scenarios like robots taking over the world are intriguing because they are now part of our societal dialogue, no longer relegated to the fringes. This shift signifies the significant value AI will bring.

## Future Agentic Systems and Transition to New Technologies
When we see that uptake, we'll see more investment, we'll start to solve these problems, we'll find new ways of solving those problems, will reinvent the paradigm. In 10 or 20 years, we'll actually start to have things that can truly be agentic, where they can formulate hypotheses, create actions, execute actions, observe consequences, update hypothesis generation, and then actually start to do that in a stable way through very complex behavioral circumstances. I look at this on a much longer arc of time where I see it now, 10 years ago, I didn't know how we're going to get there, but now I think we have some bits and pieces. We have some of the primitives in place that we can actually do this. It may take 100 MW to do it, not 20 W of energy like your brain, but that's progress. I'm super excited and pumped about this. When I'm 80 years old and looking back, we will have really made a dent and completely changed the world. That's very exciting.

It is frustrating that the transition is a long-term process, not just a short-term one like 10 years, but more like a 100-year transition. It was exciting to be part of the early adopters of AI, advocating for its importance when no one believed in it. Now, with success and recognition, it's easier to explain my work, but it can also be annoying as everyone wants to discuss their own theories and seek my opinion constantly.

## Creating Meaningful Change through Technology and Excitement for the Future
But overall, I think I'm very happy and excited about where the world is going. Being the sideshow is never as fun, but you can get passion from that. When everyone tells you you're the sideshow, you have to be passionate to keep going. You can use that as strength. The point of having passion and strength is to make something meaningful, something that really changes the course of human evolution. I'm here to be a part of building the next set of technologies that make humans able to influence the world in greater ways. Hopefully, you enjoyed listening to Convened as much as we enjoyed speaking with him. More exciting episodes are coming, along with more from the A 16 Z archive. Subscribe to the feed so you don't miss them. Thank you for listening.
