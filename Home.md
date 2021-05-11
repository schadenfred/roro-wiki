Rolling your web application into source control using a service like Github or Bitbucket and from there onto Heroku is a great way to prototype, but once you move to production with customers and traffic it can get complicated and expensive and difficult to get away.

RoRo is not a service, but a collection of development stories. A story can be how to set up a Rails app using Docker Compose, or it can be about setting that same app up with CI/CD and deploying it to a kubernetes cluster using Digital Ocean. RoRo gives you a set of conventions and tools to securely re-enact these stories, write your own stories, and then share them with your development team or the open source community writ large.

**Conventions**
1. All of your work for a project lives in a dedicated folder somewhere in your path. You don't have to call this project folder your 'bench,' but that's what we'll call it here.
2. Roro must be a folder at the same level as your apps on your bench such that if your project is an app called 'Petunia':
`
$ ls 
roro petunia
`
3. Each of your apps must have a matching folder in roro/containers such that if you have a Rails app called 'Petunia' such that:
`$ ls`
 
Your app lives in a separate folder in your bench.
Environment variables shared by more than one of your apps across all environments live in roro/env/base.env
Environment variables shared by more than one of your apps in just one environment, where 'staging' is the name of your environment live in roro/env/staging.env 

 and are namespaced according to the name of their environment. 

