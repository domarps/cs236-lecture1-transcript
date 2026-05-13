# Stanford CS236: Deep Generative Models I 2023 | Lecture 1 - Introduction



Video: https://youtu.be/XZ0PMRWXBEU



This transcript was generated locally with Whisper `large-v3-turbo`. Each timestamp links to the matching point in the lecture.



[00:00](https://youtu.be/XZ0PMRWXBEU?t=0s) Welcome.

[00:05](https://youtu.be/XZ0PMRWXBEU?t=5s) I'm super excited to see so many people interested in deep generative models.

[00:13](https://youtu.be/XZ0PMRWXBEU?t=13s) So I'm Stefano, I'm the instructor of this class.

[00:17](https://youtu.be/XZ0PMRWXBEU?t=17s) I've been teaching this course for a few years now.

[00:20](https://youtu.be/XZ0PMRWXBEU?t=20s) I guess we started back when before all the generative AI hype

[00:26](https://youtu.be/XZ0PMRWXBEU?t=26s) and before this topic was so popular in the industry.

[00:30](https://youtu.be/XZ0PMRWXBEU?t=30s) And so now you're lucky, you get to experience a pretty mature version of this course.

[00:37](https://youtu.be/XZ0PMRWXBEU?t=37s) And it's going to be a pretty exciting quarter.

[00:42](https://youtu.be/XZ0PMRWXBEU?t=42s) This is one of the hottest topics in industry right now.

[00:47](https://youtu.be/XZ0PMRWXBEU?t=47s) There is of course a lot of excitement around the language models,

[00:50](https://youtu.be/XZ0PMRWXBEU?t=50s) about generative models of images, of videos.

[00:53](https://youtu.be/XZ0PMRWXBEU?t=53s) And the goal of this class is to give you really the foundations

[00:57](https://youtu.be/XZ0PMRWXBEU?t=57s) to understand how the methods that are used in industry and in academic papers actually work.

[01:04](https://youtu.be/XZ0PMRWXBEU?t=64s) And hopefully get up to speed with all the really fundamental concepts that you need

[01:12](https://youtu.be/XZ0PMRWXBEU?t=72s) in order to build a generative model.

[01:14](https://youtu.be/XZ0PMRWXBEU?t=74s) And maybe in the future develop better systems, develop better models,

[01:19](https://youtu.be/XZ0PMRWXBEU?t=79s) deploy them in industry, start your own company that is sort of like leveraging these technologies.

[01:26](https://youtu.be/XZ0PMRWXBEU?t=86s) So at a high level, you know, one of the reasons I think these models are becoming so important in AI and machine learning

[01:37](https://youtu.be/XZ0PMRWXBEU?t=97s) is that they really address kind of like the fundamental challenge that we encounter in a lot of subfields of AI,

[01:44](https://youtu.be/XZ0PMRWXBEU?t=104s) like computer vision, NLP, computational speech, even robotics, and so forth.

[01:52](https://youtu.be/XZ0PMRWXBEU?t=112s) If you think about it in a lot of these settings, the fundamental challenge that you have is to make sense of some complex high dimensional signal or object,

[02:03](https://youtu.be/XZ0PMRWXBEU?t=123s) like an image or a speech signal or a sequence of tokens or a sequence of characters written in some language.

[02:12](https://youtu.be/XZ0PMRWXBEU?t=132s) And this is challenging because, you know, from the perspective of a computer, if you think about an image,

[02:18](https://youtu.be/XZ0PMRWXBEU?t=138s) it's just like a big matrix of numbers.

[02:20](https://youtu.be/XZ0PMRWXBEU?t=140s) And the difficulty is making sense of it, trying to figure out how to map that very complex high dimensional object

[02:27](https://youtu.be/XZ0PMRWXBEU?t=147s) to some kind of representation that is useful for decision making, for a variety of tasks that we care about,

[02:36](https://youtu.be/XZ0PMRWXBEU?t=156s) like figuring out what kind of objects are in the image or what kind of relationships they are in,

[02:42](https://youtu.be/XZ0PMRWXBEU?t=162s) what kind of materials they are made of, if they are moving, how fast, things like that.

[02:47](https://youtu.be/XZ0PMRWXBEU?t=167s) And, you know, similarly, if you think about NLP, it's a similar story.

[02:51](https://youtu.be/XZ0PMRWXBEU?t=171s) You have a sequence of characters and you need to make sense of it.

[02:54](https://youtu.be/XZ0PMRWXBEU?t=174s) You need to understand what's the meaning, and maybe you want to translate it in a different language.

[02:59](https://youtu.be/XZ0PMRWXBEU?t=179s) The challenge is really understanding what these complex objects really mean.

[03:05](https://youtu.be/XZ0PMRWXBEU?t=185s) And understanding these objects is hard.

[03:09](https://youtu.be/XZ0PMRWXBEU?t=189s) It's not even clear what it means to understand what an image means.

[03:13](https://youtu.be/XZ0PMRWXBEU?t=193s) But I like to use this analogy inspired by this quote from Richard Feynman.

[03:19](https://youtu.be/XZ0PMRWXBEU?t=199s) At some point he said, what I cannot create, I do not understand.

[03:24](https://youtu.be/XZ0PMRWXBEU?t=204s) I think this was actually what they found on his whiteboard after he passed.

[03:29](https://youtu.be/XZ0PMRWXBEU?t=209s) And, you know, what he meant in this case is that he was talking about mathematical theorems,

[03:36](https://youtu.be/XZ0PMRWXBEU?t=216s) and he was saying, if I can't really derive a proof by myself, I'm not really understanding the concept well enough.

[03:43](https://youtu.be/XZ0PMRWXBEU?t=223s) But I think the analogy is that we can look at the contrapositive of this and kind of like the philosophy behind generative modeling approaches in AI is that if I claim I'm able to understand what an image means or what a piece of text means, then I should be able to create it.

[04:03](https://youtu.be/XZ0PMRWXBEU?t=243s) I should be able to generate new images, I should be able to generate new text.

[04:07](https://youtu.be/XZ0PMRWXBEU?t=247s) So if you claim you understand what an apple is, then you should be able to kind of like picture one in your head.

[04:13](https://youtu.be/XZ0PMRWXBEU?t=253s) Maybe you're not able to create a photo of an apple, but you know sort of like what it means.

[04:18](https://youtu.be/XZ0PMRWXBEU?t=258s) Or if you claim you can speak Italian, then you should be able to sort of like produce, you should be able to speak in that language, you should be able to write text in that language.

[04:29](https://youtu.be/XZ0PMRWXBEU?t=269s) And that's kind of like the philosophy behind this idea of building generative models of images or generative models of text or multimodal generative models.

[04:38](https://youtu.be/XZ0PMRWXBEU?t=278s) If you have these kind of capabilities, so you're able to generate text that is coherent, it makes sense, like in large language models like chat GPT, those kind of things.

[04:48](https://youtu.be/XZ0PMRWXBEU?t=288s) And it probably means that you have a certain level of understanding, not only of the rules, the grammar of the language, but also about common sense, about what's going on in the world.

[05:01](https://youtu.be/XZ0PMRWXBEU?t=301s) And essentially the only way you can do a good job of generating text that is meaningful is to have a certain level of understanding.

[05:09](https://youtu.be/XZ0PMRWXBEU?t=309s) And if you have that level of understanding, then you can leverage it and you can use it to solve all the tasks that we care about.

[05:17](https://youtu.be/XZ0PMRWXBEU?t=317s) So how do we go about building software, writing code that can generate, let's say, images or can generate text?

[05:28](https://youtu.be/XZ0PMRWXBEU?t=328s) You know, this is not necessarily a new problem.

[05:33](https://youtu.be/XZ0PMRWXBEU?t=333s) It's not something that we are looking at for the first time.

[05:36](https://youtu.be/XZ0PMRWXBEU?t=336s) People in computer graphics, for example, have been thinking about writing code that can generate images for a very long time.

[05:44](https://youtu.be/XZ0PMRWXBEU?t=344s) And they made a lot of progress in this space.

[05:47](https://youtu.be/XZ0PMRWXBEU?t=347s) And so you can kind of think of the setting as something like where you're given a high level description of a scene.

[05:55](https://youtu.be/XZ0PMRWXBEU?t=355s) Maybe there are different kinds of objects of different colors, different shapes.

[06:00](https://youtu.be/XZ0PMRWXBEU?t=360s) Maybe you have a viewpoint.

[06:02](https://youtu.be/XZ0PMRWXBEU?t=362s) And the goal is to kind of like write a renderer that can produce an image that corresponds to that high level description.

[06:13](https://youtu.be/XZ0PMRWXBEU?t=373s) And again, the idea is that if you can do this, then you probably have a reasonable understanding of what it means, what the concept of a cube is, what the concept of a cylinder is, what colors mean, relative position.

[06:30](https://youtu.be/XZ0PMRWXBEU?t=390s) And in fact, if you can do this well, then you can imagine a procedure where you try to invert this process.

[06:37](https://youtu.be/XZ0PMRWXBEU?t=397s) And you know, given an image, you can try to figure out what was the high level description that produced this scene.

[06:45](https://youtu.be/XZ0PMRWXBEU?t=405s) And to the extent that you don't have sort of like computational constraints and you can do this efficiently, this gives you a way to think about computer vision in terms of inverse graphics.

[06:57](https://youtu.be/XZ0PMRWXBEU?t=417s) So if you have a process that can generate images well, and you are somehow able to invert it, then you are making progress towards computer vision tasks because you are able to really understand these high level descriptions of the scenes.

[07:13](https://youtu.be/XZ0PMRWXBEU?t=433s) And this is not going to be a course on computer graphics.

[07:18](https://youtu.be/XZ0PMRWXBEU?t=438s) We are going to be looking at very different kind of models, but they will have a similar structure.

[07:23](https://youtu.be/XZ0PMRWXBEU?t=443s) Many of them will have a similar structure where there is going to be a generative component.

[07:27](https://youtu.be/XZ0PMRWXBEU?t=447s) And then often there is going to be latent variables that you can kind of like infer given the raw sensory inputs in this case.

[07:35](https://youtu.be/XZ0PMRWXBEU?t=455s) And you can use that to get features, to get representations.

[07:40](https://youtu.be/XZ0PMRWXBEU?t=460s) You can use them to fine tune your models, to solve computer vision tasks.

[07:46](https://youtu.be/XZ0PMRWXBEU?t=466s) And so this kind of philosophy and this kind of structure will actually show up in the kind of models that we'll build in the class.

[07:55](https://youtu.be/XZ0PMRWXBEU?t=475s) So the kind of models we're going to work on, they are not graphics based.

[08:00](https://youtu.be/XZ0PMRWXBEU?t=480s) They are going to be statistical models.

[08:02](https://youtu.be/XZ0PMRWXBEU?t=482s) So we're only going to be talking about models that are based on machine learning techniques.

[08:08](https://youtu.be/XZ0PMRWXBEU?t=488s) And so the generative models that we're going to work with are going to be based on a combination of data and prior knowledge.

[08:15](https://youtu.be/XZ0PMRWXBEU?t=495s) And so, you know, priors are always necessary.

[08:20](https://youtu.be/XZ0PMRWXBEU?t=500s) But you can imagine that there is a spectrum, right?

[08:23](https://youtu.be/XZ0PMRWXBEU?t=503s) You can rely more on data.

[08:25](https://youtu.be/XZ0PMRWXBEU?t=505s) You can rely more on priors.

[08:27](https://youtu.be/XZ0PMRWXBEU?t=507s) And you can kind of like think of computer graphics as sort of like lying on this extreme,

[08:33](https://youtu.be/XZ0PMRWXBEU?t=513s) where you leverage a lot of knowledge about physics, about light transport, about properties of objects to come up with good renderers.

[08:42](https://youtu.be/XZ0PMRWXBEU?t=522s) This course is going to be focusing on methods that are much more data driven, where we're going to be trying to use as little prior knowledge as possible,

[08:51](https://youtu.be/XZ0PMRWXBEU?t=531s) and instead leverage data.

[08:54](https://youtu.be/XZ0PMRWXBEU?t=534s) Large data sets of images or text, perhaps collected on the internet.

[08:59](https://youtu.be/XZ0PMRWXBEU?t=539s) And, yeah, so at a very high level, these generative models are just going to be probability distributions over, let's say, images x, or over sequences of text x.

[09:16](https://youtu.be/XZ0PMRWXBEU?t=556s) And so in that sense, they are statistical.

[09:18](https://youtu.be/XZ0PMRWXBEU?t=558s) And we're going to be building these models using a combination of data, which you can think of as samples from this probability distribution.

[09:27](https://youtu.be/XZ0PMRWXBEU?t=567s) And in this case, the prior knowledge is basically going to be a mix of the kind of architectures you're going to be using,

[09:35](https://youtu.be/XZ0PMRWXBEU?t=575s) the kind of loss functions that you're going to be using for training the models,

[09:38](https://youtu.be/XZ0PMRWXBEU?t=578s) the kind of optimizer that you're going to be using to try to produce the loss function as much as possible.

[09:45](https://youtu.be/XZ0PMRWXBEU?t=585s) And this combination, having access to good data and the right kind of like priors, is what enables you to build, hopefully, a good statistical generative model.

[09:58](https://youtu.be/XZ0PMRWXBEU?t=598s) But at the end of the day, kind of like the abstraction is that we're going to be working with probability distributions.

[10:05](https://youtu.be/XZ0PMRWXBEU?t=605s) And you can just think of it as a function that takes any input x as input, let's say any image, and maps it to some kind of like scalar probability value,

[10:14](https://youtu.be/XZ0PMRWXBEU?t=614s) which basically tells you how likely is this particular input image x according to my generative model.

[10:23](https://youtu.be/XZ0PMRWXBEU?t=623s) And this might not look like a generative model directly.

[10:29](https://youtu.be/XZ0PMRWXBEU?t=629s) It looks like how do you actually generate data if you have access to this kind of object.

[10:34](https://youtu.be/XZ0PMRWXBEU?t=634s) The idea is that you can basically generate samples from this probability distribution to create new objects.

[10:41](https://youtu.be/XZ0PMRWXBEU?t=641s) So you train a model, you learn this probability distribution, and then you sample from it.

[10:46](https://youtu.be/XZ0PMRWXBEU?t=646s) And by doing that, you generate new images that hopefully look like the ones you've used for training the model.

[10:55](https://youtu.be/XZ0PMRWXBEU?t=655s) So that's the structure.

[10:57](https://youtu.be/XZ0PMRWXBEU?t=657s) So in some sense, what we're trying to do is we're trying to build data simulators.

[11:02](https://youtu.be/XZ0PMRWXBEU?t=662s) So we often think of data as an input to our machine learning problems.

[11:07](https://youtu.be/XZ0PMRWXBEU?t=667s) Here we're kind of like changing, turning things around, and we're thinking of data as being an output.

[11:13](https://youtu.be/XZ0PMRWXBEU?t=673s) So we need to think about different kinds of machine learning models that we can use to simulate, to generate data.

[11:21](https://youtu.be/XZ0PMRWXBEU?t=681s) Of course, this looks a little bit weird because we just said we're going to use data to build these models.

[11:26](https://youtu.be/XZ0PMRWXBEU?t=686s) So indeed, you know, the idea is that we're going to use data to build a model that then we can use to generate new data.

[11:33](https://youtu.be/XZ0PMRWXBEU?t=693s) And this is useful because often we're going to be interested in simulators that we can control through control signals.

[11:42](https://youtu.be/XZ0PMRWXBEU?t=702s) And we'll see some examples of the kind of control signals you might want to use to control your generative process.

[11:50](https://youtu.be/XZ0PMRWXBEU?t=710s) For example, you might have a model that can generate images, and you can control it by providing a caption of the kind of images you want.

[11:59](https://youtu.be/XZ0PMRWXBEU?t=719s) Or you might have a model that can, again, generate images, and you can control it by providing maybe black and white images, and you can use it to produce a colorized version of the image.

[12:11](https://youtu.be/XZ0PMRWXBEU?t=731s) Or maybe you have a data simulator that can produce text in English, and you can control the generative process by feeding in text in a different language, maybe in Chinese.

[12:21](https://youtu.be/XZ0PMRWXBEU?t=741s) That's how you build machine translation tools.

[12:27](https://youtu.be/XZ0PMRWXBEU?t=747s) The API is going to be, again, that of a probability distribution.

[12:31](https://youtu.be/XZ0PMRWXBEU?t=751s) So really, you're going to be able to, for a lot of these models, you're going to be able to also query the model with potential data points.

[12:40](https://youtu.be/XZ0PMRWXBEU?t=760s) And the model will be able to tell you whether or not they are likely to be generated by this data simulator or not.

[12:46](https://youtu.be/XZ0PMRWXBEU?t=766s) So in some sense, it also allows you to build a sort of understanding over what kind of data points make sense and which ones don't, which is going to be useful for some applications.

[12:56](https://youtu.be/XZ0PMRWXBEU?t=776s) And really, this data simulator is, at the end of the day, a statistical model.

[13:01](https://youtu.be/XZ0PMRWXBEU?t=781s) It's what we call in machine learning a generative model.

[13:04](https://youtu.be/XZ0PMRWXBEU?t=784s) And in particular, in this class, we're going to be thinking about deep generative models,

[13:08](https://youtu.be/XZ0PMRWXBEU?t=788s) where we're going to be using neural networks, deep learning kind of ideas to implement this piece of code that gives you these capabilities of generating data.

[13:19](https://youtu.be/XZ0PMRWXBEU?t=799s) And to give you a few examples, if you have a generative model of images, you might be able to control it, let's say, using sketches.

[13:31](https://youtu.be/XZ0PMRWXBEU?t=811s) Maybe you're not good at painting, and you can only produce a rough sketch of a bedroom, and then you fit it as a control signal into your generative model,

[13:41](https://youtu.be/XZ0PMRWXBEU?t=821s) and you can use it to produce realistic images that have the structure of the stroke painting that you provide, but they look much better.

[13:51](https://youtu.be/XZ0PMRWXBEU?t=831s) Or you can do maybe text-to-image kind of things, where if you have a generative model that has been trained on paintings,

[13:58](https://youtu.be/XZ0PMRWXBEU?t=838s) then you can control it through captions, and you can ask the model to generate a new painting that corresponds to the description that is provided by the user.

[14:08](https://youtu.be/XZ0PMRWXBEU?t=848s) Other examples that you might not think about immediately could be something like you have a generative model over medical images.

[14:18](https://youtu.be/XZ0PMRWXBEU?t=858s) And in this case, you might use an actual signal coming from an MRI machine or a CT scan machine,

[14:24](https://youtu.be/XZ0PMRWXBEU?t=864s) and you can use that signal to sort of reconstruct the medical image, the thing you actually care about,

[14:31](https://youtu.be/XZ0PMRWXBEU?t=871s) given this kind of measurement that is coming from an actual machine.

[14:36](https://youtu.be/XZ0PMRWXBEU?t=876s) And in this kind of application, generative models have shown to be very effective,

[14:42](https://youtu.be/XZ0PMRWXBEU?t=882s) because they can reduce kind of like the number of measurements, the amount of radiation that you have to give to the patient

[14:50](https://youtu.be/XZ0PMRWXBEU?t=890s) to get a measurement that is good enough to produce the medical images that the doctor needs to come up with a diagnosis.

[14:57](https://youtu.be/XZ0PMRWXBEU?t=897s) An example of the kind of thing you can do if you can evaluate probabilities is to do outlier detection.

[15:06](https://youtu.be/XZ0PMRWXBEU?t=906s) Actually, they're going to be playing with this in the homework, a variant of this.

[15:10](https://youtu.be/XZ0PMRWXBEU?t=910s) If you have a generative model that understands traffic signs, you might be able to say,

[15:16](https://youtu.be/XZ0PMRWXBEU?t=916s) OK, this looks like a reasonable traffic sign you might encounter on the streets.

[15:21](https://youtu.be/XZ0PMRWXBEU?t=921s) Well, if I feed you something like this, some kind of adversarial example,

[15:25](https://youtu.be/XZ0PMRWXBEU?t=925s) somebody's trying to cause trouble to your self-driving vehicle, the model might be able to say,

[15:32](https://youtu.be/XZ0PMRWXBEU?t=932s) no, this looks like a low probability thing, this is weird, do something about it, maybe don't trust it,

[15:38](https://youtu.be/XZ0PMRWXBEU?t=938s) ask a human for help, or something like that.

[15:41](https://youtu.be/XZ0PMRWXBEU?t=941s) Right, and this is really an exciting time to study generative models,

[15:47](https://youtu.be/XZ0PMRWXBEU?t=947s) because there's been a lot of progress over many different modalities.

[15:53](https://youtu.be/XZ0PMRWXBEU?t=953s) I'm going to start with images, because that's where I've done a lot of my research.

[15:59](https://youtu.be/XZ0PMRWXBEU?t=959s) When I started working in this space about 10 years ago, these were the sort of images that we were able to generate.

[16:06](https://youtu.be/XZ0PMRWXBEU?t=966s) And even that was already very, very remarkable.

[16:10](https://youtu.be/XZ0PMRWXBEU?t=970s) People were very surprised that it was possible to train machine learning systems to produce images of people

[16:18](https://youtu.be/XZ0PMRWXBEU?t=978s) that sort of are black and white, and they roughly had the right shape.

[16:23](https://youtu.be/XZ0PMRWXBEU?t=983s) People were very impressed by those sort of results.

[16:26](https://youtu.be/XZ0PMRWXBEU?t=986s) And you can see that over a few years, this progress was largely driven by generative adversarial networks,

[16:33](https://youtu.be/XZ0PMRWXBEU?t=993s) which is a class of generative models we're going to be talking about.

[16:37](https://youtu.be/XZ0PMRWXBEU?t=997s) You can kind of see how the generations are becoming better and better, higher resolution, more detail,

[16:42](https://youtu.be/XZ0PMRWXBEU?t=1002s) more realistic kind of images of people.

[16:45](https://youtu.be/XZ0PMRWXBEU?t=1005s) One of the big improvements that happened over the last two or three years,

[16:51](https://youtu.be/XZ0PMRWXBEU?t=1011s) which was actually largely coming out of Stanford, Yang Song, who was a PhD student in my group,

[16:58](https://youtu.be/XZ0PMRWXBEU?t=1018s) came up with this idea of using score-based diffusion models,

[17:04](https://youtu.be/XZ0PMRWXBEU?t=1024s) which is a different kind of generative models that we're also going to be talking about in this course,

[17:09](https://youtu.be/XZ0PMRWXBEU?t=1029s) and was able to further push the state of the art, for example, generating images very high,

[17:14](https://youtu.be/XZ0PMRWXBEU?t=1034s) resolution images that look like this.

[17:17](https://youtu.be/XZ0PMRWXBEU?t=1037s) Like these people don't exist.

[17:19](https://youtu.be/XZ0PMRWXBEU?t=1039s) They are completely synthesized, generated by one of these generative models.

[17:25](https://youtu.be/XZ0PMRWXBEU?t=1045s) And this is really, diffusion models are really the technology that drives a lot of the text-to-image systems that you might have seen.

[17:37](https://youtu.be/XZ0PMRWXBEU?t=1057s) Things like stable diffusion, or DALI, or other, or mid-journey, we think are all based on this type of generative model,

[17:49](https://youtu.be/XZ0PMRWXBEU?t=1069s) this way of representing probability distribution based on a diffusion model.

[17:54](https://youtu.be/XZ0PMRWXBEU?t=1074s) And once you have a good diffusion model, you can try to control it using captions.

[18:00](https://youtu.be/XZ0PMRWXBEU?t=1080s) And now you get this kind of really cool text-to-image systems where you can ask a user for an input.

[18:09](https://youtu.be/XZ0PMRWXBEU?t=1089s) What kind of image do you want? A caption of what kind of image the system should be able to produce.

[18:15](https://youtu.be/XZ0PMRWXBEU?t=1095s) For example, an astronaut riding a horse.

[18:18](https://youtu.be/XZ0PMRWXBEU?t=1098s) And these are the kind of results that you can get with the systems we have today.

[18:24](https://youtu.be/XZ0PMRWXBEU?t=1104s) This is really cool.

[18:26](https://youtu.be/XZ0PMRWXBEU?t=1106s) I mean, these models have been trained on a lot of data,

[18:30](https://youtu.be/XZ0PMRWXBEU?t=1110s) but presumably they have not seen something like this on the internet.

[18:36](https://youtu.be/XZ0PMRWXBEU?t=1116s) They might have seen an astronaut, they definitely have seen a horse,

[18:39](https://youtu.be/XZ0PMRWXBEU?t=1119s) but they probably have not seen those two things together.

[18:42](https://youtu.be/XZ0PMRWXBEU?t=1122s) So it's very impressive that the model is able to, sort of like, again, understand the meaning of astronaut,

[18:48](https://youtu.be/XZ0PMRWXBEU?t=1128s) understand the meaning of horse, putting them together.

[18:51](https://youtu.be/XZ0PMRWXBEU?t=1131s) And the fact that it's able to generate this kind of picture tells me that there is some level of understanding of what it means,

[18:59](https://youtu.be/XZ0PMRWXBEU?t=1139s) what an astronaut means, and what riding means, what a horse means.

[19:03](https://youtu.be/XZ0PMRWXBEU?t=1143s) And even, like, if you look at the landscape, I don't know, it could be,

[19:07](https://youtu.be/XZ0PMRWXBEU?t=1147s) it feels like it's probably on some other planet or something.

[19:11](https://youtu.be/XZ0PMRWXBEU?t=1151s) So there is some level of understanding about these concepts that it's showing here.

[19:16](https://youtu.be/XZ0PMRWXBEU?t=1156s) And that's super exciting, I think, because it means that we're really making progress in this space

[19:23](https://youtu.be/XZ0PMRWXBEU?t=1163s) and understanding the meaning of text, of images, that relationship.

[19:26](https://youtu.be/XZ0PMRWXBEU?t=1166s) And that's what's driving a lot of the successes that we're seeing in ML these days.

[19:33](https://youtu.be/XZ0PMRWXBEU?t=1173s) Here's another example.

[19:35](https://youtu.be/XZ0PMRWXBEU?t=1175s) If you ask a system on a perfect Italian meal, you get, here I'm generating multiple samples.

[19:41](https://youtu.be/XZ0PMRWXBEU?t=1181s) So, because it's a probability distribution, as you can imagine, you can sample from it.

[19:46](https://youtu.be/XZ0PMRWXBEU?t=1186s) And it will generate different answers.

[19:48](https://youtu.be/XZ0PMRWXBEU?t=1188s) So the generation is stochastic.

[19:50](https://youtu.be/XZ0PMRWXBEU?t=1190s) Different random see it, it will produce different outputs every time.

[19:54](https://youtu.be/XZ0PMRWXBEU?t=1194s) I see, we can see four of them.

[19:56](https://youtu.be/XZ0PMRWXBEU?t=1196s) Again, I think it does a pretty good job.

[19:58](https://youtu.be/XZ0PMRWXBEU?t=1198s) I mean, some of the stuff is clearly made up, but it does, it's interesting how it kind of like even captures out of the window

[20:05](https://youtu.be/XZ0PMRWXBEU?t=1205s) the kind of buildings you would probably see in Italy.

[20:13](https://youtu.be/XZ0PMRWXBEU?t=1213s) It kind of like has the right flavor, I think.

[20:16](https://youtu.be/XZ0PMRWXBEU?t=1216s) It's pretty impressive kind of thing.

[20:19](https://youtu.be/XZ0PMRWXBEU?t=1219s) Here's another example from a recent system developed in China.

[20:25](https://youtu.be/XZ0PMRWXBEU?t=1225s) This is a teddy bear wearing a costume, standing in front of the Hall of Supreme Harmony and singing a Beijing opera.

[20:32](https://youtu.be/XZ0PMRWXBEU?t=1232s) So again, a pretty crazy sort of caption.

[20:35](https://youtu.be/XZ0PMRWXBEU?t=1235s) And it produces things like this.

[20:38](https://youtu.be/XZ0PMRWXBEU?t=1238s) Pretty impressive.

[20:45](https://youtu.be/XZ0PMRWXBEU?t=1245s) And this is the latest that came out very recently.

[20:50](https://youtu.be/XZ0PMRWXBEU?t=1250s) We don't know yet what this model is built on.

[20:53](https://youtu.be/XZ0PMRWXBEU?t=1253s) Dali3 from OpenAI, this is an example from their blog post.

[20:57](https://youtu.be/XZ0PMRWXBEU?t=1257s) Here you're asking the model to generate.

[21:05](https://youtu.be/XZ0PMRWXBEU?t=1265s) Well, you can see the caption yourself.

[21:09](https://youtu.be/XZ0PMRWXBEU?t=1269s) Pretty cool.

[21:10](https://youtu.be/XZ0PMRWXBEU?t=1270s) Again, demonstrates a pretty sophisticated level of understanding of concepts and a good way of combining them together.

[21:20](https://youtu.be/XZ0PMRWXBEU?t=1280s) Right, so this is a test to image generation.

[21:23](https://youtu.be/XZ0PMRWXBEU?t=1283s) Again, the nice thing about these models is that you can often control them using different kinds of control signals.

[21:30](https://youtu.be/XZ0PMRWXBEU?t=1290s) So here we're controlling using text, using captions.

[21:33](https://youtu.be/XZ0PMRWXBEU?t=1293s) But there is a lot of inverse problems.

[21:36](https://youtu.be/XZ0PMRWXBEU?t=1296s) Again, this is a field that has been studied for a long time.

[21:40](https://youtu.be/XZ0PMRWXBEU?t=1300s) People have been thinking about how to colorize an image, how to do super resolution on an image, how to do in-painting on an image.

[21:47](https://youtu.be/XZ0PMRWXBEU?t=1307s) These problems become pretty much easier to solve once you have a good system that really understands the relationship between all the pixel values that you typically see in an image.

[22:01](https://youtu.be/XZ0PMRWXBEU?t=1321s) And so there's been a lot of progress in, let's say, super resolution.

[22:06](https://youtu.be/XZ0PMRWXBEU?t=1326s) You go from low resolution images like this to high resolution images like that.

[22:10](https://youtu.be/XZ0PMRWXBEU?t=1330s) Or colorization.

[22:11](https://youtu.be/XZ0PMRWXBEU?t=1331s) You can take old black and white photos and you can kind of like colorize them in a meaningful way.

[22:17](https://youtu.be/XZ0PMRWXBEU?t=1337s) Or in-painting.

[22:18](https://youtu.be/XZ0PMRWXBEU?t=1338s) So if you have an image where some of the pixels are masked out, you can ask the model to fill them in.

[22:25](https://youtu.be/XZ0PMRWXBEU?t=1345s) And they do a pretty good job at doing this.

[22:29](https://youtu.be/XZ0PMRWXBEU?t=1349s) These are probably not the most up-to-date references.

[22:32](https://youtu.be/XZ0PMRWXBEU?t=1352s) But you can kind of get a sense of why these models are so useful in the real world.

[22:39](https://youtu.be/XZ0PMRWXBEU?t=1359s) And here's an example from SDEdit, which is one of the things that, again, one of my PhD students developed.

[22:47](https://youtu.be/XZ0PMRWXBEU?t=1367s) This is back to the sketch to image, where you can start with a sketch.

[22:51](https://youtu.be/XZ0PMRWXBEU?t=1371s) Sort of like a painting or an image that you would like.

[22:54](https://youtu.be/XZ0PMRWXBEU?t=1374s) The kind of thing I would be able to do.

[22:56](https://youtu.be/XZ0PMRWXBEU?t=1376s) And then you can ask the model to refine it and produce some pretty picture that kind of like has the right structure.

[23:03](https://youtu.be/XZ0PMRWXBEU?t=1383s) But that's much nicer.

[23:05](https://youtu.be/XZ0PMRWXBEU?t=1385s) I would never be able to produce the image at the bottom.

[23:08](https://youtu.be/XZ0PMRWXBEU?t=1388s) But I could probably come up with a sketch you see on the top.

[23:13](https://youtu.be/XZ0PMRWXBEU?t=1393s) And yeah, here you can see more examples where you can do sketch to image.

[23:18](https://youtu.be/XZ0PMRWXBEU?t=1398s) Or you can do even stroke-based editing.

[23:20](https://youtu.be/XZ0PMRWXBEU?t=1400s) Maybe you start with an image and then you want to change it based on some rough sense of what you want the image to have.

[23:29](https://youtu.be/XZ0PMRWXBEU?t=1409s) And then the model will make it pretty for you.

[23:34](https://youtu.be/XZ0PMRWXBEU?t=1414s) And it doesn't have to be editing or sort of like you don't have to control it through strokes.

[23:40](https://youtu.be/XZ0PMRWXBEU?t=1420s) Another natural way of controlling this kind of editing process is through text.

[23:46](https://youtu.be/XZ0PMRWXBEU?t=1426s) So instead of actually drawing what you want, you can ask the model, you can tell the model how you want your images to be edited.

[23:54](https://youtu.be/XZ0PMRWXBEU?t=1434s) So you might start with an image of a bird, but now you want to change it so that you want it to spread the wings.

[24:01](https://youtu.be/XZ0PMRWXBEU?t=1441s) And you can tell the model how to spread the wings.

[24:03](https://youtu.be/XZ0PMRWXBEU?t=1443s) And it's able to do this kind of update.

[24:06](https://youtu.be/XZ0PMRWXBEU?t=1446s) Or you have an image with two birds and now you want the birds to be kissing.

[24:09](https://youtu.be/XZ0PMRWXBEU?t=1449s) And then this is what you produce.

[24:12](https://youtu.be/XZ0PMRWXBEU?t=1452s) Or you have an image with a box and now you want the box to be open.

[24:15](https://youtu.be/XZ0PMRWXBEU?t=1455s) And you can kind of see some pretty impressive results in terms of image editing or changing the pose of this dog.

[24:24](https://youtu.be/XZ0PMRWXBEU?t=1464s) Or even changing the style of the painting of the image.

[24:27](https://youtu.be/XZ0PMRWXBEU?t=1467s) You go from a real image to some kind of like drawings.

[24:32](https://youtu.be/XZ0PMRWXBEU?t=1472s) And again, it does a pretty good job.

[24:34](https://youtu.be/XZ0PMRWXBEU?t=1474s) You can see it's making some mistakes.

[24:36](https://youtu.be/XZ0PMRWXBEU?t=1476s) Like this knife here gets changed in a way that is not quite what we want.

[24:43](https://youtu.be/XZ0PMRWXBEU?t=1483s) They are not perfect yet.

[24:45](https://youtu.be/XZ0PMRWXBEU?t=1485s) But these capabilities are very impressive.

[24:47](https://youtu.be/XZ0PMRWXBEU?t=1487s) Already very useful.

[24:51](https://youtu.be/XZ0PMRWXBEU?t=1491s) Cool.

[24:52](https://youtu.be/XZ0PMRWXBEU?t=1492s) And yeah, back to the more exotic one that you might not necessarily think fits in this framework.

[24:58](https://youtu.be/XZ0PMRWXBEU?t=1498s) Just to give you a sense of how general these ideas are.

[25:02](https://youtu.be/XZ0PMRWXBEU?t=1502s) If you have a generative model of medical images, you can use it to essentially improve the way we do medical images.

[25:12](https://youtu.be/XZ0PMRWXBEU?t=1512s) In this case, the control signal, it's an actual measurement that you get from, let's say, a CT scan machine.

[25:18](https://youtu.be/XZ0PMRWXBEU?t=1518s) And then you can control the generative process using the measurement from the CT scan machine.

[25:24](https://youtu.be/XZ0PMRWXBEU?t=1524s) And this can drastically reduce the amount of radiations.

[25:28](https://youtu.be/XZ0PMRWXBEU?t=1528s) And the number of measurements that you need to get a crisp kind of image that you can show to the doctor.

[25:34](https://youtu.be/XZ0PMRWXBEU?t=1534s) This is very similar to in-painting.

[25:36](https://youtu.be/XZ0PMRWXBEU?t=1536s) It's just in-painting in a slightly different space.

[25:38](https://youtu.be/XZ0PMRWXBEU?t=1538s) You can kind of get a sense.

[25:40](https://youtu.be/XZ0PMRWXBEU?t=1540s) It's roughly the same problem.

[25:42](https://youtu.be/XZ0PMRWXBEU?t=1542s) And advances in generative models translate into big improvements in this real-world applications.

[25:49](https://youtu.be/XZ0PMRWXBEU?t=1549s) All right.

[25:53](https://youtu.be/XZ0PMRWXBEU?t=1553s) Now, moving on to different modalities.

[25:55](https://youtu.be/XZ0PMRWXBEU?t=1555s) Speech audio has been another modality where people have been able to build some pretty good generative models.

[26:03](https://youtu.be/XZ0PMRWXBEU?t=1563s) This is one of the earliest ones.

[26:07](https://youtu.be/XZ0PMRWXBEU?t=1567s) The WaveNet model back, I think it was 2016.

[26:10](https://youtu.be/XZ0PMRWXBEU?t=1570s) And you can kind of see some examples of, let's hope this works.

[26:16](https://youtu.be/XZ0PMRWXBEU?t=1576s) This is an example.

[26:22](https://youtu.be/XZ0PMRWXBEU?t=1582s) This is kind of like the pre-deep learning thing.

[26:25](https://youtu.be/XZ0PMRWXBEU?t=1585s) And these are not great text-to-speech.

[26:28](https://youtu.be/XZ0PMRWXBEU?t=1588s) The Blue Lagoon is a 1980 American romance and adventure film directed by Randall Kleiser.

[26:33](https://youtu.be/XZ0PMRWXBEU?t=1593s) And then the WaveNet model, which is a deep learning-based model for text-to-speech.

[26:38](https://youtu.be/XZ0PMRWXBEU?t=1598s) You're going to see it's significantly better.

[26:40](https://youtu.be/XZ0PMRWXBEU?t=1600s) The Blue Lagoon is a 1980 American romance and adventure film directed by Randall Kleiser.

[26:45](https://youtu.be/XZ0PMRWXBEU?t=1605s) And these are maybe the latest ones that are based on diffusion models again.

[26:52](https://youtu.be/XZ0PMRWXBEU?t=1612s) So this is, well, this is a combination of diffusion models and autoregressive models.

[26:57](https://youtu.be/XZ0PMRWXBEU?t=1617s) But here you can see some of the 2023 stuff.

[27:00](https://youtu.be/XZ0PMRWXBEU?t=1620s) Once you have the first token, you want to predict the second token given the input and the first token using multi-head attention.

[27:08](https://youtu.be/XZ0PMRWXBEU?t=1628s) You can see it's much more realistic.

[27:11](https://youtu.be/XZ0PMRWXBEU?t=1631s) There is a little bit of an accent here.

[27:14](https://youtu.be/XZ0PMRWXBEU?t=1634s) There is a little bit of emotions that are, it feels a lot less robotic, a lot less fake.

[27:21](https://youtu.be/XZ0PMRWXBEU?t=1641s) Here's another example.

[27:23](https://youtu.be/XZ0PMRWXBEU?t=1643s) This is text-to-speech.

[27:25](https://youtu.be/XZ0PMRWXBEU?t=1645s) You input a text and you produce the speech corresponding to that text.

[27:30](https://youtu.be/XZ0PMRWXBEU?t=1650s) CS-236 is the best class at Stanford.

[27:33](https://youtu.be/XZ0PMRWXBEU?t=1653s) So this is another example.

[27:36](https://youtu.be/XZ0PMRWXBEU?t=1656s) And again, you can sort of like use these things to solve inverse problems.

[27:42](https://youtu.be/XZ0PMRWXBEU?t=1662s) So you can do super resolution in the audio space.

[27:45](https://youtu.be/XZ0PMRWXBEU?t=1665s) So you can condition on the kind of like a low quality signal, the kind of thing you can get maybe on phones.

[27:53](https://youtu.be/XZ0PMRWXBEU?t=1673s) One is investment, one is reform.

[27:57](https://youtu.be/XZ0PMRWXBEU?t=1677s) And then you can super resolve it.

[27:59](https://youtu.be/XZ0PMRWXBEU?t=1679s) One is investment, one is reform.

[28:02](https://youtu.be/XZ0PMRWXBEU?t=1682s) Again, this is the same problem as basically in painting.

[28:05](https://youtu.be/XZ0PMRWXBEU?t=1685s) Like you're missing some pixels, you're missing some frequencies, and you can ask the model to make them up for you.

[28:10](https://youtu.be/XZ0PMRWXBEU?t=1690s) And to the extent that it understands the relationship between these values, which you can also kind of think of as images,

[28:18](https://youtu.be/XZ0PMRWXBEU?t=1698s) it can do a pretty good job of super resolving audio.

[28:24](https://youtu.be/XZ0PMRWXBEU?t=1704s) Language, of course, that's another space where there's been a lot of progress and a lot of excitement around large language models.

[28:33](https://youtu.be/XZ0PMRWXBEU?t=1713s) These are basically models that have been trained over large quantities of text collected on the internet often.

[28:43](https://youtu.be/XZ0PMRWXBEU?t=1723s) And then they learn a probability distribution over which sentences make sense or not.

[28:48](https://youtu.be/XZ0PMRWXBEU?t=1728s) And you can use it to, again, do some sort of in-painting where you can ask the model to create a sentence that starts with some kind of prompt.

[28:58](https://youtu.be/XZ0PMRWXBEU?t=1738s) For example, this was an old language model, I guess in 2019, I think, where you can ask the model to continue a sentence that starts with

[29:11](https://youtu.be/XZ0PMRWXBEU?t=1751s) to get an A-plus in deep generative models.

[29:14](https://youtu.be/XZ0PMRWXBEU?t=1754s) Students have to.

[29:16](https://youtu.be/XZ0PMRWXBEU?t=1756s) And then let's see what the language model does.

[29:19](https://youtu.be/XZ0PMRWXBEU?t=1759s) And then it completes it for you, right?

[29:21](https://youtu.be/XZ0PMRWXBEU?t=1761s) And then it says, it's not so much reasonable.

[29:24](https://youtu.be/XZ0PMRWXBEU?t=1764s) We have to be willing to work with problems that are all more interesting.

[29:28](https://youtu.be/XZ0PMRWXBEU?t=1768s) The past, you know, not great, not perfect for today's standards.

[29:33](https://youtu.be/XZ0PMRWXBEU?t=1773s) But again, for when this thing came out, it was pretty mind-blowing that you could build a model that can generate this quality of text.

[29:43](https://youtu.be/XZ0PMRWXBEU?t=1783s) Now, I tried something similar on ChatGPT.

[29:48](https://youtu.be/XZ0PMRWXBEU?t=1788s) And this time I tried something harder.

[29:50](https://youtu.be/XZ0PMRWXBEU?t=1790s) Like here I said to get an A-plus in deep generative models.

[29:54](https://youtu.be/XZ0PMRWXBEU?t=1794s) Here I tried what should I do to get an A-plus in CS236 at Stanford.

[29:59](https://youtu.be/XZ0PMRWXBEU?t=1799s) So I didn't even tell the model ChatGPT what CS236 is.

[30:04](https://youtu.be/XZ0PMRWXBEU?t=1804s) It actually knows that CS236 is deep generative models.

[30:09](https://youtu.be/XZ0PMRWXBEU?t=1809s) And here it gives you some actually pretty good tips on how to do well in the class.

[30:14](https://youtu.be/XZ0PMRWXBEU?t=1814s) Attend lectures, read the materials, stay organized, seek help, do the homeworks.

[30:21](https://youtu.be/XZ0PMRWXBEU?t=1821s) Then it gives you 15 of them.

[30:23](https://youtu.be/XZ0PMRWXBEU?t=1823s) I cut the prompt here.

[30:25](https://youtu.be/XZ0PMRWXBEU?t=1825s) But, you know, it's pretty impressive that you can do these kind of things.

[30:32](https://youtu.be/XZ0PMRWXBEU?t=1832s) And again, it probably means that there is some level of understanding.

[30:37](https://youtu.be/XZ0PMRWXBEU?t=1837s) And that's why these models are so powerful when people are using them for doing all sorts of things.

[30:43](https://youtu.be/XZ0PMRWXBEU?t=1843s) Because they can generate.

[30:44](https://youtu.be/XZ0PMRWXBEU?t=1844s) It means they understand something.

[30:46](https://youtu.be/XZ0PMRWXBEU?t=1846s) And then you can use the knowledge to solve a variety of tasks that we care about.

[30:51](https://youtu.be/XZ0PMRWXBEU?t=1851s) Of course, the nice thing about this space is that you can often mix and match.

[31:02](https://youtu.be/XZ0PMRWXBEU?t=1862s) And so you can kind of control these models using various sorts of control signals.

[31:09](https://youtu.be/XZ0PMRWXBEU?t=1869s) Once you can do generation, you can steer the generative process using different control signals.

[31:15](https://youtu.be/XZ0PMRWXBEU?t=1875s) A natural one here would be generate text in English conditioned on some text in a different language.

[31:23](https://youtu.be/XZ0PMRWXBEU?t=1883s) So maybe Chinese.

[31:25](https://youtu.be/XZ0PMRWXBEU?t=1885s) So you have, and this basically is machine translation, right?

[31:30](https://youtu.be/XZ0PMRWXBEU?t=1890s) So progress is in generative models.

[31:32](https://youtu.be/XZ0PMRWXBEU?t=1892s) Basically directly translated to progress in machine translation.

[31:36](https://youtu.be/XZ0PMRWXBEU?t=1896s) If you have a model that really understands how to generate text in English,

[31:41](https://youtu.be/XZ0PMRWXBEU?t=1901s) then it can take advantage of the control signal well.

[31:45](https://youtu.be/XZ0PMRWXBEU?t=1905s) Then it means that essentially it's able to do the retranslation reasonably well.

[31:50](https://youtu.be/XZ0PMRWXBEU?t=1910s) And a lot of the progress in terms of like the models and the architectures that we're going to talk about in this class

[31:56](https://youtu.be/XZ0PMRWXBEU?t=1916s) are the kind of ideas that are behind the pretty good machine translation systems that we have today.

[32:03](https://youtu.be/XZ0PMRWXBEU?t=1923s) Another example is code.

[32:08](https://youtu.be/XZ0PMRWXBEU?t=1928s) Of course, very exciting as it's computer science.

[32:11](https://youtu.be/XZ0PMRWXBEU?t=1931s) Many of you are computer scientists, so write a lot of code.

[32:14](https://youtu.be/XZ0PMRWXBEU?t=1934s) At the end of the day, code is text.

[32:17](https://youtu.be/XZ0PMRWXBEU?t=1937s) If you have a model that understands which sequences of text make sense and which ones don't,

[32:24](https://youtu.be/XZ0PMRWXBEU?t=1944s) you can use it to write code for you.

[32:27](https://youtu.be/XZ0PMRWXBEU?t=1947s) So here's an example of a system that exists today where you're kind of like creating a code.

[32:33](https://youtu.be/XZ0PMRWXBEU?t=1953s) You can try to get the model to autocomplete, let's say, the body of a function based on some description of what the function is supposed to do.

[32:42](https://youtu.be/XZ0PMRWXBEU?t=1962s) Again, these systems are not perfect, but they are already pretty good.

[32:49](https://youtu.be/XZ0PMRWXBEU?t=1969s) They can solve many interesting tasks.

[32:54](https://youtu.be/XZ0PMRWXBEU?t=1974s) They can solve programming assignments.

[32:59](https://youtu.be/XZ0PMRWXBEU?t=1979s) They can solve competition.

[33:01](https://youtu.be/XZ0PMRWXBEU?t=1981s) They do reasonably well in competitive programming competitions.

[33:07](https://youtu.be/XZ0PMRWXBEU?t=1987s) So, again, pretty cool that they understand the natural language.

[33:13](https://youtu.be/XZ0PMRWXBEU?t=1993s) They understand the syntax of the programming language.

[33:15](https://youtu.be/XZ0PMRWXBEU?t=1995s) They know how to put things together so that they do the right thing.

[33:19](https://youtu.be/XZ0PMRWXBEU?t=1999s) They're sort of able to translate, in this case, from natural language to a formal language,

[33:23](https://youtu.be/XZ0PMRWXBEU?t=2003s) and Python in this case, and do the right thing.

[33:28](https://youtu.be/XZ0PMRWXBEU?t=2008s) So lots of excitement also around these sort of models.

[33:36](https://youtu.be/XZ0PMRWXBEU?t=2016s) Another one that is pretty cool is video.

[33:39](https://youtu.be/XZ0PMRWXBEU?t=2019s) This is one of the active ones where the first systems are being built.

[33:45](https://youtu.be/XZ0PMRWXBEU?t=2025s) Again, you can imagine a variety of different interfaces where you can control the generative process through many different things.

[33:53](https://youtu.be/XZ0PMRWXBEU?t=2033s) A natural one is text.

[33:55](https://youtu.be/XZ0PMRWXBEU?t=2035s) You might say you start with a caption, and then you ask the model to generate a video corresponding to that caption.

[34:07](https://youtu.be/XZ0PMRWXBEU?t=2047s) This is one example.

[34:09](https://youtu.be/XZ0PMRWXBEU?t=2049s) The videos are pretty short right now.

[34:11](https://youtu.be/XZ0PMRWXBEU?t=2051s) That's one of the limitations.

[34:13](https://youtu.be/XZ0PMRWXBEU?t=2053s) But can you see it?

[34:16](https://youtu.be/XZ0PMRWXBEU?t=2056s) Oh, yeah, it shows up there.

[34:18](https://youtu.be/XZ0PMRWXBEU?t=2058s) Here's another example.

[34:21](https://youtu.be/XZ0PMRWXBEU?t=2061s) Here they're asking it to generate a video of a couple sledding down a snowy hill on the Roman Church's style.

[34:30](https://youtu.be/XZ0PMRWXBEU?t=2070s) And this is sort of like what it produces.

[34:34](https://youtu.be/XZ0PMRWXBEU?t=2074s) Pretty short videos.

[34:37](https://youtu.be/XZ0PMRWXBEU?t=2077s) At the end of the day, you kind of think of a video as a sequence of images.

[34:41](https://youtu.be/XZ0PMRWXBEU?t=2081s) So if you can generate images, it's believable that you can also generate a stack of images, which is essentially a video.

[34:49](https://youtu.be/XZ0PMRWXBEU?t=2089s) Pretty impressive.

[34:51](https://youtu.be/XZ0PMRWXBEU?t=2091s) There's a good amount of coherence across the frames.

[34:55](https://youtu.be/XZ0PMRWXBEU?t=2095s) It captures roughly what's asked by the user.

[34:58](https://youtu.be/XZ0PMRWXBEU?t=2098s) And the quality is pretty high.

[35:01](https://youtu.be/XZ0PMRWXBEU?t=2101s) And if you're willing to work on this and stitch together many different videos, you can generate some pretty cool stuff.

[35:09](https://youtu.be/XZ0PMRWXBEU?t=2109s) That's the example.

[35:11](https://youtu.be/XZ0PMRWXBEU?t=2111s) That's the example.

[35:12](https://youtu.be/XZ0PMRWXBEU?t=2112s) That's the example.

[35:14](https://youtu.be/XZ0PMRWXBEU?t=2114s) languages.

[35:20](https://youtu.be/XZ0PMRWXBEU?t=2120s) l

[35:44](https://youtu.be/XZ0PMRWXBEU?t=2144s) This is just basically stitching together a bunch of videos generated with the previous system.

[35:55](https://youtu.be/XZ0PMRWXBEU?t=2155s) And, you know, again, you can see it's not perfect, but it's remarkable.

[36:02](https://youtu.be/XZ0PMRWXBEU?t=2162s) I mean, we're not at the level where you can just ask the system to produce a movie for you

[36:08](https://youtu.be/XZ0PMRWXBEU?t=2167s) with a certain plot or whatever, with your favorite actor,

[36:11](https://youtu.be/XZ0PMRWXBEU?t=2171s) but it's already able to produce pretty high-quality content that people are willing to look at and engage with.

[36:18](https://youtu.be/XZ0PMRWXBEU?t=2178s) So that's an exciting kind of development that we're seeing in generative models of videos.

[36:24](https://youtu.be/XZ0PMRWXBEU?t=2183s) I think when that starts to work, and we're seeing the kind of progress in this space that I showed you before for images,

[36:30](https://youtu.be/XZ0PMRWXBEU?t=2189s) it's happening right now.

[36:31](https://youtu.be/XZ0PMRWXBEU?t=2191s) I think when people figure this out and get really good systems, they can generate long videos of high quality.

[36:37](https://youtu.be/XZ0PMRWXBEU?t=2197s) This could be really changing the way we, you know, a lot of the media industry is going to have to pay attention to this.

[36:51](https://youtu.be/XZ0PMRWXBEU?t=2210s) Question? Yeah.

[36:53](https://youtu.be/XZ0PMRWXBEU?t=2212s) Yeah.

[36:53](https://youtu.be/XZ0PMRWXBEU?t=2212s) Yeah.

[36:53](https://youtu.be/XZ0PMRWXBEU?t=2213s) Yeah.

[36:54](https://youtu.be/XZ0PMRWXBEU?t=2213s) Yeah.

[36:55](https://youtu.be/XZ0PMRWXBEU?t=2215s) I feel like you have to give some intentings, like, you know, some hand sketches, because nowadays I would say this is the most impressive video generation.

[37:09](https://youtu.be/XZ0PMRWXBEU?t=2229s) Video ever, ever saying so.

[37:11](https://youtu.be/XZ0PMRWXBEU?t=2230s) Because I would keep following this.

[37:12](https://youtu.be/XZ0PMRWXBEU?t=2232s) So it's, I mean, these ones are generated purely from the caption.

[37:15](https://youtu.be/XZ0PMRWXBEU?t=2235s) Okay.

[37:16](https://youtu.be/XZ0PMRWXBEU?t=2235s) This one, I don't know exactly what went into this.

[37:20](https://youtu.be/XZ0PMRWXBEU?t=2240s) I didn't make it myself.

[37:22](https://youtu.be/XZ0PMRWXBEU?t=2242s) But I know the system allows you to also control it through a caption and a seed image.

[37:30](https://youtu.be/XZ0PMRWXBEU?t=2250s) So, you know, if you maybe already know what you want your character to look like, then you can kind of use it and animate, let's say, a given image.

[37:40](https://youtu.be/XZ0PMRWXBEU?t=2260s) And again, it's an example of controlling the generative process.

[37:45](https://youtu.be/XZ0PMRWXBEU?t=2264s) Like, you can control it through text.

[37:47](https://youtu.be/XZ0PMRWXBEU?t=2266s) You can control it through images.

[37:48](https://youtu.be/XZ0PMRWXBEU?t=2268s) There are many different ways to do this.

[37:54](https://youtu.be/XZ0PMRWXBEU?t=2273s) Yeah.

[37:54](https://youtu.be/XZ0PMRWXBEU?t=2274s) And this is actually from a PhD student, a former PhD student in our group.

[38:00](https://youtu.be/XZ0PMRWXBEU?t=2280s) So, yeah, it's a system that they are developing.

[38:03](https://youtu.be/XZ0PMRWXBEU?t=2283s) It's very good.

[38:04](https://youtu.be/XZ0PMRWXBEU?t=2283s) I agree with you.

[38:06](https://youtu.be/XZ0PMRWXBEU?t=2286s) Pretty impressive stuff.

[38:08](https://youtu.be/XZ0PMRWXBEU?t=2287s) So that's the kind of thing you can do once you learn this material very well.

[38:15](https://youtu.be/XZ0PMRWXBEU?t=2294s) All right.

[38:15](https://youtu.be/XZ0PMRWXBEU?t=2295s) Other completely different sort of application area, sort of like decision-making, robotics.

[38:23](https://youtu.be/XZ0PMRWXBEU?t=2303s) This kind of, a lot of these domains, what you care about is taking actions in the world to achieve a certain goal.

[38:32](https://youtu.be/XZ0PMRWXBEU?t=2312s) Let's say driving a car or stacking some objects.

[38:35](https://youtu.be/XZ0PMRWXBEU?t=2314s) And so at the end of the day, you can think of it as generating a sequence of actions that make sense.

[38:40](https://youtu.be/XZ0PMRWXBEU?t=2320s) And so, again, the kind of machinery that we're going to talk about in this course translates pretty well to a lot of what we call imitation learning problems,

[38:52](https://youtu.be/XZ0PMRWXBEU?t=2331s) where you are given examples of good behavior provided maybe by a human.

[38:56](https://youtu.be/XZ0PMRWXBEU?t=2335s) And you want your model to generate other behaviors that are good.

[39:00](https://youtu.be/XZ0PMRWXBEU?t=2340s) For example, you want the model to learn how to drive the car or how to stack objects.

[39:05](https://youtu.be/XZ0PMRWXBEU?t=2345s) And so here's an example of how you can kind of like use these sort of techniques that we're going to talk about in the course to learn how to drive the car in this video game.

[39:17](https://youtu.be/XZ0PMRWXBEU?t=2356s) And you have to figure out, of course, what sort of actions make sense and to not crash into other cars and stay on the road and so forth.

[39:28](https://youtu.be/XZ0PMRWXBEU?t=2367s) This is non-trivial, again, but if you have a good generative model, then you can make good decisions in this simulator.

[39:36](https://youtu.be/XZ0PMRWXBEU?t=2376s) This is an example where you can kind of like train a diffusion model in this case to stack objects.

[39:44](https://youtu.be/XZ0PMRWXBEU?t=2383s) So, again, you sort of like need to figure out what sort of trajectories make sense.

[39:47](https://youtu.be/XZ0PMRWXBEU?t=2387s) And if you have a good model that understands which trajectories have the right structure,

[39:51](https://youtu.be/XZ0PMRWXBEU?t=2390s) then you can use it to stack a different set of objects and you can control the model to produce high-quality policies.

[40:00](https://youtu.be/XZ0PMRWXBEU?t=2399s) There's a lot of excitement in the scientific science and engineering around generative models.

[40:08](https://youtu.be/XZ0PMRWXBEU?t=2407s) One of your TAs is one of the world's experts on using generative models to synthesize molecules that have certain properties or like proteins that have certain properties.

[40:19](https://youtu.be/XZ0PMRWXBEU?t=2419s) And either on the level of their structure or even at the 3D level, can I really understand the layout of these molecules.

[40:30](https://youtu.be/XZ0PMRWXBEU?t=2430s) And, yeah, there is a lot of interest in this space around building generative models to design drugs or to design better catalysts.

[40:42](https://youtu.be/XZ0PMRWXBEU?t=2441s) So, at the end of the day, you can think of it as, again, some kind of generative model where you have to come up with a recipe that does well at a certain task.

[40:50](https://youtu.be/XZ0PMRWXBEU?t=2450s) And if you have trained a model on a lot of data on what kind of, let's say, proteins perform well in a certain task,

[40:58](https://youtu.be/XZ0PMRWXBEU?t=2458s) then you might be able to generate a sequence of amino acids that perform even better than the things we have.

[41:04](https://youtu.be/XZ0PMRWXBEU?t=2464s) Or you might be able to design a drug that binds in a certain way because you're targeting, let's say, COVID or something.

[41:12](https://youtu.be/XZ0PMRWXBEU?t=2472s) And so there is a lot of interest around building generative models over modalities that are somewhat different from the typical ones.

[41:23](https://youtu.be/XZ0PMRWXBEU?t=2482s) It's not images. It's not text.

[41:24](https://youtu.be/XZ0PMRWXBEU?t=2484s) But it's the same generative models.

[41:26](https://youtu.be/XZ0PMRWXBEU?t=2486s) It's still diffusion models.

[41:28](https://youtu.be/XZ0PMRWXBEU?t=2487s) There's going to be autoregressive models.

[41:30](https://youtu.be/XZ0PMRWXBEU?t=2489s) It's going to be the kind of models we're going to talk about in this course.

[41:37](https://youtu.be/XZ0PMRWXBEU?t=2496s) And, right, so lots of excitement.

[41:41](https://youtu.be/XZ0PMRWXBEU?t=2500s) There is other, you know, many other modalities that I didn't put in this LIDAC where there's been progress generating 3D objects.

[41:53](https://youtu.be/XZ0PMRWXBEU?t=2512s) That's another very exciting kind of like area and many more.

[41:59](https://youtu.be/XZ0PMRWXBEU?t=2518s) Of course, there is also a bit of worry.

[42:04](https://youtu.be/XZ0PMRWXBEU?t=2523s) And hopefully we'll get to talk about it a bit in the class around, you know, computers are getting so good at generating content that it's hard to distinguish from the real one.

[42:17](https://youtu.be/XZ0PMRWXBEU?t=2537s) You know, there is this big issue around deepfakes.

[42:20](https://youtu.be/XZ0PMRWXBEU?t=2539s) You know, which one is real, which one is fake?

[42:22](https://youtu.be/XZ0PMRWXBEU?t=2542s) This was produced again by my students.

[42:24](https://youtu.be/XZ0PMRWXBEU?t=2544s) I think I kind of get a sense of the sort of dangers that these kind of technologies can have.

[42:30](https://youtu.be/XZ0PMRWXBEU?t=2550s) And there is a lot of potential for misuse of these sort of systems.

[42:35](https://youtu.be/XZ0PMRWXBEU?t=2555s) So hopefully we'll get to talk about that too in the class.

[42:40](https://youtu.be/XZ0PMRWXBEU?t=2559s) So, all right.

[42:41](https://youtu.be/XZ0PMRWXBEU?t=2560s) So that was sort of like the intro.

[42:46](https://youtu.be/XZ0PMRWXBEU?t=2565s) Hopefully it got you excited about the topic.

[42:48](https://youtu.be/XZ0PMRWXBEU?t=2568s) And it kind of like showed you that it's really an exciting time to be working in this area.

[42:53](https://youtu.be/XZ0PMRWXBEU?t=2572s) And that's why there's so much excitement also in the industry and in academia around these topics.

[42:58](https://youtu.be/XZ0PMRWXBEU?t=2577s) Everybody's trying to innovate, build systems, figure out how to use them in the real world, find new applications.

[43:06](https://youtu.be/XZ0PMRWXBEU?t=2585s) So it's really an exciting time to study this.

[43:09](https://youtu.be/XZ0PMRWXBEU?t=2588s) The course is designed to really give you the, uncover the, what we think are the core concepts in this space.

[43:23](https://youtu.be/XZ0PMRWXBEU?t=2602s) Once you understand all the different building blocks, the kind of challenges, the kind of trade-offs that all these models do,

[43:30](https://youtu.be/XZ0PMRWXBEU?t=2610s) then you can not only understand how existing systems work,

[43:35](https://youtu.be/XZ0PMRWXBEU?t=2615s) but hopefully you can also, you know, design the next generation of these systems.

[43:39](https://youtu.be/XZ0PMRWXBEU?t=2618s) You can also improve them, figure out how to use them on a new application area.

[43:45](https://youtu.be/XZ0PMRWXBEU?t=2625s) Again, the system, the course is designed to be pretty rigorous.

[43:50](https://youtu.be/XZ0PMRWXBEU?t=2629s) There's going to be quite a bit of math.

[43:51](https://youtu.be/XZ0PMRWXBEU?t=2631s) It's really going to delve deep into the key ideas.

[43:56](https://youtu.be/XZ0PMRWXBEU?t=2635s) So we're going to talk a lot about representation, as we discussed.

[44:02](https://youtu.be/XZ0PMRWXBEU?t=2641s) The key building block is going to be statistical modeling.

[44:05](https://youtu.be/XZ0PMRWXBEU?t=2644s) We're going to be using probability distributions.

[44:07](https://youtu.be/XZ0PMRWXBEU?t=2646s) That's going to be the key building block.

[44:10](https://youtu.be/XZ0PMRWXBEU?t=2649s) And so we're going to talk a lot about how to represent these probability distributions,

[44:16](https://youtu.be/XZ0PMRWXBEU?t=2655s) how to use neural networks to model probability distributions,

[44:21](https://youtu.be/XZ0PMRWXBEU?t=2660s) where we have many random variables.

[44:23](https://youtu.be/XZ0PMRWXBEU?t=2663s) That is the challenge.

[44:24](https://youtu.be/XZ0PMRWXBEU?t=2664s) I mean, you've seen simple probability distributions, like Gaussians and things like that.

[44:28](https://youtu.be/XZ0PMRWXBEU?t=2668s) That doesn't work in this space because you have so many different things that you have to consider

[44:34](https://youtu.be/XZ0PMRWXBEU?t=2674s) and you have to model at the same time.

[44:36](https://youtu.be/XZ0PMRWXBEU?t=2676s) And so you need to come up with clever ways to represent how all the different pixels in an image interact with each other

[44:42](https://youtu.be/XZ0PMRWXBEU?t=2682s) or how the different words in a sentence, they are connected to each other.

[44:46](https://youtu.be/XZ0PMRWXBEU?t=2686s) And so a lot of the course content will focus on different ideas,

[44:53](https://youtu.be/XZ0PMRWXBEU?t=2693s) the different trade-offs that you have to make when you build these kind of models.

[44:59](https://youtu.be/XZ0PMRWXBEU?t=2699s) We're going to talk about learning.

[45:01](https://youtu.be/XZ0PMRWXBEU?t=2700s) Again, these are going to be statistical generative models.

[45:04](https://youtu.be/XZ0PMRWXBEU?t=2703s) So there's always going to be data, and you're going to use the data to fit the models.

[45:09](https://youtu.be/XZ0PMRWXBEU?t=2708s) And there's many different ways to fit models.

[45:12](https://youtu.be/XZ0PMRWXBEU?t=2711s) There's many different kinds of loss functions that you can use.

[45:14](https://youtu.be/XZ0PMRWXBEU?t=2714s) There's the stuff that is used in diffusion models.

[45:16](https://youtu.be/XZ0PMRWXBEU?t=2716s) There's the stuff that is used in generative adversarial networks.

[45:19](https://youtu.be/XZ0PMRWXBEU?t=2719s) There is the stuff that is used in, let's say, large language models, autoregressive models.

[45:24](https://youtu.be/XZ0PMRWXBEU?t=2724s) Those are essentially boiled down to different ways of comparing these probability distributions.

[45:29](https://youtu.be/XZ0PMRWXBEU?t=2729s) You have a data distribution.

[45:31](https://youtu.be/XZ0PMRWXBEU?t=2731s) You have the model distribution.

[45:33](https://youtu.be/XZ0PMRWXBEU?t=2732s) And you want those two things to be similar so that when you generate samples from the model,

[45:38](https://youtu.be/XZ0PMRWXBEU?t=2738s) they look like the ones that came from the data distribution.

[45:43](https://youtu.be/XZ0PMRWXBEU?t=2742s) But probability distributions, again, going back to the first point, they are very complex.

[45:48](https://youtu.be/XZ0PMRWXBEU?t=2748s) If you have very complicated objects, very high-dimensional objects,

[45:53](https://youtu.be/XZ0PMRWXBEU?t=2753s) so it's not straightforward to compare to probability distributions

[45:56](https://youtu.be/XZ0PMRWXBEU?t=2756s) and kind of measure how similar they are.

[45:59](https://youtu.be/XZ0PMRWXBEU?t=2759s) So you have to sort of like, you have a data distribution.

[46:02](https://youtu.be/XZ0PMRWXBEU?t=2761s) You have a family of models that you can pick from.

[46:04](https://youtu.be/XZ0PMRWXBEU?t=2764s) And you kind of like have to pick one that is close to the data.

[46:08](https://youtu.be/XZ0PMRWXBEU?t=2767s) But measuring similarity is very difficult.

[46:12](https://youtu.be/XZ0PMRWXBEU?t=2772s) And depending on how you measure similarity, you're going to get different kinds of models

[46:16](https://youtu.be/XZ0PMRWXBEU?t=2775s) that work well in different kinds of scenarios.

[46:20](https://youtu.be/XZ0PMRWXBEU?t=2779s) And then we're going to talk about inference.

[46:22](https://youtu.be/XZ0PMRWXBEU?t=2781s) We're going to talk about, you know, how to generate samples from these models efficiently.

[46:27](https://youtu.be/XZ0PMRWXBEU?t=2786s) Sometimes you have the probability distribution, but it might not be straightforward to sample from it.

[46:32](https://youtu.be/XZ0PMRWXBEU?t=2792s) So we will talk about that.

[46:34](https://youtu.be/XZ0PMRWXBEU?t=2794s) We will talk about how to invert the generative process,

[46:37](https://youtu.be/XZ0PMRWXBEU?t=2797s) how to get representations from these objects.

[46:41](https://youtu.be/XZ0PMRWXBEU?t=2800s) For example, kind of like, sort of like, following and making the idea of vision as inverse graphic a little bit more concrete.

[46:51](https://youtu.be/XZ0PMRWXBEU?t=2811s) So we'll touch on unsupervised learning, different ways of sort of like clustering.

[46:57](https://youtu.be/XZ0PMRWXBEU?t=2817s) Because at the end of the day, what these models do is they have to find similarity between data points.

[47:03](https://youtu.be/XZ0PMRWXBEU?t=2822s) When you're trying to complete a sentence, what you have to do is you have to go through your training set.

[47:08](https://youtu.be/XZ0PMRWXBEU?t=2828s) You have to find similar sentences.

[47:10](https://youtu.be/XZ0PMRWXBEU?t=2829s) You have to figure out how to combine them.

[47:11](https://youtu.be/XZ0PMRWXBEU?t=2830s) And you have to figure out how to complete the prompt that you're given.

[47:16](https://youtu.be/XZ0PMRWXBEU?t=2835s) So once you have generative models, you can usually also get sort of like representations.

[47:22](https://youtu.be/XZ0PMRWXBEU?t=2842s) You have ways of clustering data points that have similar meaning.

[47:27](https://youtu.be/XZ0PMRWXBEU?t=2846s) And again, you can get features.

[47:29](https://youtu.be/XZ0PMRWXBEU?t=2848s) And you can do kind of like the sort of things you would want to do in unsupervised learning,

[47:33](https://youtu.be/XZ0PMRWXBEU?t=2853s) which is do machine learning when you don't have labels.

[47:37](https://youtu.be/XZ0PMRWXBEU?t=2856s) You only have the X, but you don't have the Y.

[47:42](https://youtu.be/XZ0PMRWXBEU?t=2862s) And you want to do interesting things with the features themselves.

[47:50](https://youtu.be/XZ0PMRWXBEU?t=2869s) And so those are sort of like the three key ideas that are going to show up quite a bit.

[47:56](https://youtu.be/XZ0PMRWXBEU?t=2875s) In terms of models, we're going to be talking about first perhaps the simplest kind of model,

[48:05](https://youtu.be/XZ0PMRWXBEU?t=2885s) which is one where essentially you have access to a likelihood directly.

[48:11](https://youtu.be/XZ0PMRWXBEU?t=2891s) And there's going to be two kinds of models in this space,

[48:16](https://youtu.be/XZ0PMRWXBEU?t=2895s) autoregressive models and flow-based models.

[48:18](https://youtu.be/XZ0PMRWXBEU?t=2898s) Autoregressive models are the ones used in large language models

[48:21](https://youtu.be/XZ0PMRWXBEU?t=2901s) and a few of other systems that I talked about today.

[48:26](https://youtu.be/XZ0PMRWXBEU?t=2905s) Flow-based models are a different kind of idea that is often used for images

[48:32](https://youtu.be/XZ0PMRWXBEU?t=2911s) and other kinds of continuous data.

[48:36](https://youtu.be/XZ0PMRWXBEU?t=2915s) Then we'll talk about latent variable models.

[48:38](https://youtu.be/XZ0PMRWXBEU?t=2918s) The idea of using latent variables to increase the expressive power, essentially,

[48:43](https://youtu.be/XZ0PMRWXBEU?t=2922s) of your generative models.

[48:45](https://youtu.be/XZ0PMRWXBEU?t=2924s) We'll talk about variational inference, variational learning,

[48:49](https://youtu.be/XZ0PMRWXBEU?t=2928s) the variational autoencoder, hierarchical variational autoencoders,

[48:52](https://youtu.be/XZ0PMRWXBEU?t=2932s) those sort of ideas.

[48:54](https://youtu.be/XZ0PMRWXBEU?t=2934s) We'll talk about implicit generative models.

[48:57](https://youtu.be/XZ0PMRWXBEU?t=2936s) Here the idea is that instead of representing the probability distribution, P of X,

[49:02](https://youtu.be/XZ0PMRWXBEU?t=2942s) you're going to represent the sampling process that you use to generate samples.

[49:07](https://youtu.be/XZ0PMRWXBEU?t=2947s) And that has trade-offs.

[49:09](https://youtu.be/XZ0PMRWXBEU?t=2948s) It allows you to generate samples very efficiently,

[49:12](https://youtu.be/XZ0PMRWXBEU?t=2952s) but it becomes difficult to train the models

[49:15](https://youtu.be/XZ0PMRWXBEU?t=2954s) because you don't have access to a likelihood anymore.

[49:18](https://youtu.be/XZ0PMRWXBEU?t=2958s) So you cannot use maximum likelihood estimation,

[49:21](https://youtu.be/XZ0PMRWXBEU?t=2961s) those kind of ideas that we understand very well.

[49:25](https://youtu.be/XZ0PMRWXBEU?t=2964s) And we know have good performance.

[49:28](https://youtu.be/XZ0PMRWXBEU?t=2968s) So we'll talk about two sample tests,

[49:31](https://youtu.be/XZ0PMRWXBEU?t=2970s) F divergencies and different ways of training these sort of systems.

[49:34](https://youtu.be/XZ0PMRWXBEU?t=2974s) And in particular, we'll talk about generative adversarial networks

[49:39](https://youtu.be/XZ0PMRWXBEU?t=2978s) and how to train them.

[49:41](https://youtu.be/XZ0PMRWXBEU?t=2981s) Then we'll talk about energy-based models and diffusion models.

[49:46](https://youtu.be/XZ0PMRWXBEU?t=2985s) Again, this is sort of like a state-of-the-art

[49:49](https://youtu.be/XZ0PMRWXBEU?t=2988s) in terms of like image generation, audio generation.

[49:52](https://youtu.be/XZ0PMRWXBEU?t=2992s) People are starting to use them also for text.

[49:56](https://youtu.be/XZ0PMRWXBEU?t=2996s) That's what's the technology behind the video generation

[49:59](https://youtu.be/XZ0PMRWXBEU?t=2998s) that I showed you before.

[50:01](https://youtu.be/XZ0PMRWXBEU?t=3001s) So we'll talk in depth about how they work

[50:03](https://youtu.be/XZ0PMRWXBEU?t=3003s) and how you can think of them in terms of a latent variable model

[50:06](https://youtu.be/XZ0PMRWXBEU?t=3006s) and the connections with all the other things.

[50:10](https://youtu.be/XZ0PMRWXBEU?t=3010s) And, yeah, again, it's going to be a fairly mathematical class.

[50:15](https://youtu.be/XZ0PMRWXBEU?t=3015s) So there's going to be a lot of theory.

[50:17](https://youtu.be/XZ0PMRWXBEU?t=3017s) There's going to be algorithms.

[50:19](https://youtu.be/XZ0PMRWXBEU?t=3019s) And I will go through applications.

[50:22](https://youtu.be/XZ0PMRWXBEU?t=3022s) There is going to be homeworks.

[50:24](https://youtu.be/XZ0PMRWXBEU?t=3023s) We're going to get to play around with these models.

[50:25](https://youtu.be/XZ0PMRWXBEU?t=3025s) And, yeah, so in terms of prereqs,

[50:32](https://youtu.be/XZ0PMRWXBEU?t=3031s) we're expecting you to have taken at least a machine learning class.

[50:37](https://youtu.be/XZ0PMRWXBEU?t=3037s) We'll try to cover, try to do as much as possible from scratch,

[50:41](https://youtu.be/XZ0PMRWXBEU?t=3041s) and we'll have some sections to go over some of the background content.

[50:45](https://youtu.be/XZ0PMRWXBEU?t=3044s) But it might be pretty hard to take this class if you've never done any ML before.

[50:50](https://youtu.be/XZ0PMRWXBEU?t=3050s) So you should be familiar with basic probability theory, calculus.

[50:59](https://youtu.be/XZ0PMRWXBEU?t=3058s) We're going to use gradient descent, linear algebra, Bayes' rule,

[51:04](https://youtu.be/XZ0PMRWXBEU?t=3063s) those sort of things, basic calculus sort of stuff,

[51:08](https://youtu.be/XZ0PMRWXBEU?t=3067s) change of variable formula.

[51:10](https://youtu.be/XZ0PMRWXBEU?t=3070s) Yeah, you should be familiar with that.

[51:13](https://youtu.be/XZ0PMRWXBEU?t=3072s) Again, you can probably pick it up,

[51:14](https://youtu.be/XZ0PMRWXBEU?t=3074s) but it might be pretty tricky if you've never seen this sort of ideas before.

[51:19](https://youtu.be/XZ0PMRWXBEU?t=3078s) And then, yeah, there is going to be programming assignments.

[51:24](https://youtu.be/XZ0PMRWXBEU?t=3083s) So you should be familiar with, hopefully, Python.

[51:28](https://youtu.be/XZ0PMRWXBEU?t=3087s) That's what we're going to use, PyTorch.

[51:29](https://youtu.be/XZ0PMRWXBEU?t=3089s) So, again, we'll have a section on that if you've never seen it before.

[51:34](https://youtu.be/XZ0PMRWXBEU?t=3093s) But it might be tricky if you've not done any of this before.

[51:39](https://youtu.be/XZ0PMRWXBEU?t=3099s) And in terms of logistics, we have a website.

[51:43](https://youtu.be/XZ0PMRWXBEU?t=3103s) It's not entirely updated.

[51:46](https://youtu.be/XZ0PMRWXBEU?t=3105s) Some of the information might change.

[51:49](https://youtu.be/XZ0PMRWXBEU?t=3109s) So keep checking it.

[51:51](https://youtu.be/XZ0PMRWXBEU?t=3111s) We're finalizing some of the dates,

[51:53](https://youtu.be/XZ0PMRWXBEU?t=3112s) and we're trying to get confirmation about the rooms for the midterm and the poster session.

[51:58](https://youtu.be/XZ0PMRWXBEU?t=3118s) But hopefully that will be done soon.

[52:00](https://youtu.be/XZ0PMRWXBEU?t=3119s) We don't have a textbook.

[52:04](https://youtu.be/XZ0PMRWXBEU?t=3124s) That actually doesn't exist.

[52:07](https://youtu.be/XZ0PMRWXBEU?t=3127s) This was actually, I think, the first class when it was offered here a few years ago on this topic.

[52:14](https://youtu.be/XZ0PMRWXBEU?t=3133s) Nothing like that existed, so we had to create it from scratch.

[52:17](https://youtu.be/XZ0PMRWXBEU?t=3136s) And we put together a set of lecture notes that you can have access there,

[52:22](https://youtu.be/XZ0PMRWXBEU?t=3142s) where we try to cover what we, basically, the content that you can see in the slides.

[52:30](https://youtu.be/XZ0PMRWXBEU?t=3150s) Some of it, you can see some of the content is covered in the deep learning book that you can see there.

[52:38](https://youtu.be/XZ0PMRWXBEU?t=3157s) So that's a useful reference.

[52:40](https://youtu.be/XZ0PMRWXBEU?t=3159s) It's available online, so you might want to check it out.

[52:42](https://youtu.be/XZ0PMRWXBEU?t=3161s) And, yeah, we have a great team of teaching assistants.

[52:48](https://youtu.be/XZ0PMRWXBEU?t=3168s) And, yeah, there should be a calendar now on the website with our office hours.

[52:54](https://youtu.be/XZ0PMRWXBEU?t=3174s) So, of course, you're welcome to...

[52:58](https://youtu.be/XZ0PMRWXBEU?t=3177s) Most of them will start next week.

[52:59](https://youtu.be/XZ0PMRWXBEU?t=3179s) But, yeah, otherwise feel free to reach out on Ed if you cannot find us in person this week.

[53:10](https://youtu.be/XZ0PMRWXBEU?t=3189s) But, yeah, we're always happy to chat.

[53:13](https://youtu.be/XZ0PMRWXBEU?t=3193s) In terms of grading and coursework, so it's going to be three homeworks.

[53:22](https://youtu.be/XZ0PMRWXBEU?t=3202s) So the first one is going to be released Monday, next week.

[53:28](https://youtu.be/XZ0PMRWXBEU?t=3207s) And they are worth 15% of the total grade each, 45% total.

[53:34](https://youtu.be/XZ0PMRWXBEU?t=3214s) And they go over a mix of theory.

[53:38](https://youtu.be/XZ0PMRWXBEU?t=3218s) And, again, there's going to be a programming assignment associated with all of them.

[53:43](https://youtu.be/XZ0PMRWXBEU?t=3223s) We're going to have a midterm.

[53:44](https://youtu.be/XZ0PMRWXBEU?t=3224s) It's going to be in-class, in-person midterm.

[53:48](https://youtu.be/XZ0PMRWXBEU?t=3227s) And the big component of the class is going to be a project.

[53:51](https://youtu.be/XZ0PMRWXBEU?t=3231s) We think there is so much to do in this space that it makes sense for you to really explore.

[53:56](https://youtu.be/XZ0PMRWXBEU?t=3236s) There is going to account for, you know, 40% of the grades.

[54:03](https://youtu.be/XZ0PMRWXBEU?t=3243s) It's going to be a pretty significant component.

[54:06](https://youtu.be/XZ0PMRWXBEU?t=3245s) And there's a bunch of milestones.

[54:08](https://youtu.be/XZ0PMRWXBEU?t=3248s) You're going to start with a proposal.

[54:10](https://youtu.be/XZ0PMRWXBEU?t=3250s) There's going to be a report that you have kind of like to turn in about how things are going.

[54:17](https://youtu.be/XZ0PMRWXBEU?t=3257s) There's going to be a poster presentation towards the end.

[54:20](https://youtu.be/XZ0PMRWXBEU?t=3260s) And then a final report on the work you did.

[54:25](https://youtu.be/XZ0PMRWXBEU?t=3264s) And, yeah, projects.

[54:27](https://youtu.be/XZ0PMRWXBEU?t=3267s) I think I like this class, which really gives you an opportunity to explore.

[54:32](https://youtu.be/XZ0PMRWXBEU?t=3272s) And there's just so much that you can do in this space that there's lots of interesting project ideas

[54:38](https://youtu.be/XZ0PMRWXBEU?t=3277s) that turned out to be papers, turned out to be company ideas.

[54:42](https://youtu.be/XZ0PMRWXBEU?t=3282s) Lots of excitement here.

[54:44](https://youtu.be/XZ0PMRWXBEU?t=3284s) You can work in groups.

[54:46](https://youtu.be/XZ0PMRWXBEU?t=3286s) Let's say up to three students.

[54:47](https://youtu.be/XZ0PMRWXBEU?t=3287s) And typically, it's one of these three things.

[54:51](https://youtu.be/XZ0PMRWXBEU?t=3290s) Sometimes students apply an existing generative model to a new data set.

[54:56](https://youtu.be/XZ0PMRWXBEU?t=3295s) Maybe they come from an application domain,

[54:57](https://youtu.be/XZ0PMRWXBEU?t=3297s) and they find out a new interesting way to use the models on a new problem,

[55:02](https://youtu.be/XZ0PMRWXBEU?t=3301s) or they compare different generative models on a new kind of data set.

[55:07](https://youtu.be/XZ0PMRWXBEU?t=3306s) Sometimes people work on trying to just improve the models.

[55:11](https://youtu.be/XZ0PMRWXBEU?t=3311s) Again, these things are pretty new.

[55:14](https://youtu.be/XZ0PMRWXBEU?t=3313s) It's unlikely that we found the best way of solving these problems,

[55:18](https://youtu.be/XZ0PMRWXBEU?t=3317s) so there's still a lot of room for improvement.

[55:20](https://youtu.be/XZ0PMRWXBEU?t=3320s) Often, you can combine different methods.

[55:23](https://youtu.be/XZ0PMRWXBEU?t=3323s) You can take a diffusion model.

[55:25](https://youtu.be/XZ0PMRWXBEU?t=3324s) You can add a little bit of generative adversarial training flavor to it,

[55:31](https://youtu.be/XZ0PMRWXBEU?t=3330s) and you can get big improvements.

[55:32](https://youtu.be/XZ0PMRWXBEU?t=3331s) Often, these things can be published in top machine learning conferences if they work well.

[55:40](https://youtu.be/XZ0PMRWXBEU?t=3339s) And sometimes people do more theoretical analysis.

[55:43](https://youtu.be/XZ0PMRWXBEU?t=3343s) There's going to be quite a bit of theory, quite a bit of math,

[55:46](https://youtu.be/XZ0PMRWXBEU?t=3346s) and so there is room for improvement in trying to understand

[55:49](https://youtu.be/XZ0PMRWXBEU?t=3348s) why these models work, when they work, when they fail.

[55:53](https://youtu.be/XZ0PMRWXBEU?t=3352s) Right now, it's all very, very empirical,

[55:55](https://youtu.be/XZ0PMRWXBEU?t=3355s) and we really need a better theory of why things like the one I've shown you before are possible.

[56:05](https://youtu.be/XZ0PMRWXBEU?t=3365s) And so there is lots of room for developing a better theory in this space.

[56:11](https://youtu.be/XZ0PMRWXBEU?t=3370s) And we'll also be suggesting possible projects,

[56:15](https://youtu.be/XZ0PMRWXBEU?t=3375s) so look out for some information about possible projects

[56:21](https://youtu.be/XZ0PMRWXBEU?t=3380s) that can be suggested by TAs or other faculty on campus.

[56:26](https://youtu.be/XZ0PMRWXBEU?t=3385s) And we are able to provide some Google Cloud coupons.

[56:32](https://youtu.be/XZ0PMRWXBEU?t=3391s) Not much, unfortunately, but at least a little bit.

[56:35](https://youtu.be/XZ0PMRWXBEU?t=3394s) And so we'll figure out a way to distribute them to students.

[56:38](https://youtu.be/XZ0PMRWXBEU?t=3398s) And if you want to get some inspiration for what kind of projects people worked on in previous years,

[56:44](https://youtu.be/XZ0PMRWXBEU?t=3404s) you can go to the old versions of the website, the 2019 and 2021 version.

[56:51](https://youtu.be/XZ0PMRWXBEU?t=3411s) You can get a sense of the kind of projects people worked on,

[56:55](https://youtu.be/XZ0PMRWXBEU?t=3415s) and so you can get a sense of what's enough for a project,

[57:01](https://youtu.be/XZ0PMRWXBEU?t=3421s) what worked, what didn't, get some ideas.

[57:04](https://youtu.be/XZ0PMRWXBEU?t=3423s) And, yeah, I think that was pretty much what I wanted to cover today.

[57:12](https://youtu.be/XZ0PMRWXBEU?t=3431s) And I'm happy to take questions.

[57:15](https://youtu.be/XZ0PMRWXBEU?t=3435s) And then next week, we're going to start with the background of the progressive models and so forth.

[57:22](https://youtu.be/XZ0PMRWXBEU?t=3441s) So I really like to show you all the slide.

[57:23](https://youtu.be/XZ0PMRWXBEU?t=3443s) I'm happy, you know, I'll hear you there.

[57:25](https://youtu.be/XZ0PMRWXBEU?t=3444s) Thank you.

[57:25](https://youtu.be/XZ0PMRWXBEU?t=3445s) Thank you.

[57:26](https://youtu.be/XZ0PMRWXBEU?t=3446s) Thank you.
