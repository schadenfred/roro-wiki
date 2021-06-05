**keys**

Your keys live in ./roro/keys. You will need them to: 
1. Obfuscate (encrypt) plaintext environment variables so they can only 
   be accessed in the environments they're needed:
      * Share your development key with the developers on your team.
      * Share your Your CI key with your Circle or Semaphor or Github or
        whoever you handle CI/CD with.
      * Store your production key on your production server.
2. Expose (decrypt) previously obfuscated .env.enc files for other developers 
   on your team to use on their machines, 
   on your team. 
   other

**explicit single key generation** 

Given: 

    $ ls ./roro/keys/*.key

And: 
    
    $ ls ./roro/**/*.env

When:

    $ roro generate::key development 

Then:

    $ ls ./roro/keys 
    development.key 

**explicit multiple key generation** 

Given: 

    $ ls ./roro/keys/*.key

And: 

    $ ls ./roro/**/*.env

When:

    $ roro generate::keys development staging production 

Then:

    $ ls ./roro/keys 
    development.key staging.key production.key 

**implicit key generation**  

Given: 

    $ ls ./roro/keys/*.key

And:

    $ ls ./roro/env
    development.env staging.env test.env

And: 

    $ ls ./roro/containers/pistil.env 
    test.localhost.env

When:

    $ roro generate::keys

Then:

    $ ls ./roro/keys
    development.key staging.key test.key