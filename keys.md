**keys**

Your keys live in ./roro/keys and are used to obfuscate and expose sensitive directories and files. 

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