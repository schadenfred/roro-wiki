
**RoRo Conventions**

Your files for your project will live in a folder somewhere in your path. You don't need to call your folder your 'bench', you don't need to call your backend app 'Pistil' and you don't have to call your frontend app 'Stamen' -- but bench, pistil and stamen are what we'll be calling our project, backend app, and frontend for illustrative purposes here.  

**./bench** 

Your bench has a folder called roro. This folder is at the same level as pistil and stamen:
    
    $ ls 
    roro pistil stamen

**./bench/roro**

Your roro folder has folders called 'containers', 'env', 'keys', and 'scripts':

    $ ls roro
    containers env keys scripts
  
**./bench/roro/containers** 

Your roro/containers folder has subfolders for each container, service, pod, and app in your project. If your apps depend on database and redis services: 
    
    $ ls roro/containers
    database pistil redis stamen 

**./bench/roro/env**

Your roro/env folder holds environment files with environment variables shared among one or more containers. If your project has 'base', 'development', 'production', 'staging', 'test', 'test.localhost' environments: 
  
    $ ls roro/env
    base.env development.env production.env staging.env test.env test.localhost.env

**./bench/roro/containers/pistil/env**

Each of your containers have env directories of their own, each environment variables in environment files you can might use use to override project-level ones:
    
    $ ls roro/containers/petunia/env 
    base.env test.env test.localhost.env    
    
**./bench/roro/keys**

Your roro/keys folder holds keys for obfuscating and exposing different environments: 
    
    $ ls roro/keys 
    base.key development.key production.key staging.key test.key

**./bench/roro/scripts**

Your roro/scripts folder holds scripts. If you have a deploy.sh script you use on your development machine and an entrypoint.sh script only used by pistil in production: 
    
    $ ls roro/scripts -R
    development/deploy.sh 
And:
    $ ls roro/containers/pistil/scripts 
    entrypoint.sh