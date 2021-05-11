Rolling your web application into source control using a service like Github or Bitbucket and from there onto Heroku is a great way to prototype but once you move to production with customers and traffic, it can get complicated and expensive and SalesForce knows all about [vendor lock in](https://en.wikipedia.org/wiki/Vendor_lock-in).

RoRo is not a service that can lock you in but a collection of development stories. A story can be how to set up a Rails app using Docker Compose, or it can be about setting that same app up with CI/CD and deploying it to a kubernetes cluster using Digital Ocean. RoRo gives you a set of conventions and tools to securely re-enact these stories, write your own, and then share them with your development team or the open source community writ large.

**Conventions**

* All of your work for a project must live in a dedicated folder somewhere in your path. You don't have to call this project folder your 'bench,' but that's what we'll call it here.
* Roro must be a folder at the same level as your apps on your bench such that if your project is focused around an app called 'Petunia':
    `
    $ ls 
      roro petunia
    `
* RoRo must have containers, env, keys, and scripts folders such that:
    `
    $ ls roro
      containers env keys scripts
    `
* Your containers folder will have a folder for each containerized service, pod, or app such that if you have an app called petunia and a docker-compose file with petunia, database, and redis services: 
    `
    $ ls roro/containers
      database petunia redis 
    ` 
* Your env folder will hold files to be shared across all containers such that if you have different enironment files for development, production, staging, test, test on localhost and a base file for storing unimportant variables shared between all of these containers and environments: 
    ` 
    $ ls roro/env 
      base.env development.env production.env staging.env test.env test.localhost.env
    `
* Similarly each of your container folders will have their own env directory such that if you have files with variables you'd like to override those set above:
    ` 
    $ ls roro/containers/petunia/env 
      base.env development.env production.env staging.env test.env test.localhost.env    
    `




   

 and are namespaced according to the name of their environment. 

