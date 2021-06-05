Intermodal Shipping -- putting your stuff in one of those big Maersk containers on a truck and then driving it to a station and crane-ing it onto onto a ship and sailing it to a foreign port before de-crain-ing it onto a train and then to a truck and final delivery in a different country -- is a cool metaphor for how developers use containers to ship their code. It doesn't matter how much room or how much power the train, truck, or shippy on the sea has as long as it has enough for your container, just as it doesn't matter how much speed and power your machine running a hypervisor on Windows, OSX, or Ubuntu has as long as there's enough for your code container. Your code is always gonna be the same stuff inside and if the source control truck crashes, the CI / CD train derails, the image repository ship goes down in a stormy sea, or the dev-ops longshoremen go on strike, you just make changes or rollback and ship it again.

But containers don't always run alone. 

Your project might have containers for your frontend and backend, for your relational database, and for caching different things, and these containers might all need to talk to each other in order to get things done. So you want to roll your containers on and off different environments at the same time -- as a project. 

This is where RoRo comes in. RoRo is a set of tools and conventions to help you use, develop, and share your containerized project development stories with your team or with the open source community writ large. 

RoRo is focused on web application stories for WordPress, Django, Flask, and Rails, Vue, React and Node, with continuous integrations stories using Circle CI and Github and production stories using Kubernetes on Digital Ocean, Google App Engine and AWS. There will be other stories, trilogies and epics. 

Perhaps you will write one?