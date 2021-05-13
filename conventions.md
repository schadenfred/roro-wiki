
**RoRo Conventions**

Your files for your project live in a folder somewhere in your path. You don't have to call your folder your 'bench', you don't need to have to call your backend app 'Pistil,' and you don't have to call your frontend app 'Stamen' -- but bench, pistil and stamen are what we'll be calling our project, backend app, and frontend here.  

**./bench** 

Your bench has a folder called roro. This folder is at the same level as your pistil and stamen:
    
    $ ls 
    roro pistil stamen

**./bench/roro**

Your roro folder has folders called 'containers', 'env', 'keys', and 'scripts':

    $ ls roro
    containers env keys scripts
  
**./bench/roro/containers** 

Your containers folder has subfolders for each container, service, pod, or app in your project. If your apps depend on database and redis services: 
    
    $ ls roro/containers
    database pistil redis stamen 

**./bench/roro/env**

Your env folder holds environment files with environment variables shared between one or more containers. If your project has 'base', 'development', 'production', 'staging', 'test', 'test.localhost' environments: 
  
    $ ls roro/env
    base.env development.env production.env staging.env test.env test.localhost.env

**./bench/roro/containers/pistil/env**

Your containers have env directories of their own, each with environment files containing environment variables which override project-lvel environment files and variables:
    
    $ ls roro/containers/petunia/env 
    base.env development.env production.env staging.env test.env test.localhost.env    
    
**./bench/roro/keys**

Your keys folder holds keys for obfuscating and exposing different environments: 
    
    $ ls roro/keys 
    base.key development.key production.key staging.key test.key  

**./bench/roro/scripts**

Your scripts folder holds scripts. If you have a deploy.sh script you use in development:
    
    $ ls roro/scripts
    development/deploy.sh 
And if you have an entrypoint.sh script only used by pistil in production: 

    $ ls roro/containers/petunia/scripts/production/entrypoint.sh