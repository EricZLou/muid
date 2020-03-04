# muid
Memorable Unique Identifiers

## This makes no sense! 

It makes no sense for a unique identifier to be memorable. That's antithetical. 

## And yet ...
  
If you are patient, try this: 
   
    from muid.memorable import muid4, mhash, mpretty
    key  = muid4()       
    print( mhash(key) )             
    
To produce unique identifier hashed to ... (stare hard)

    f01dab1e-ca70-403a-a0c7-00f6c29596c4
    
which is within a few character translations of "readable hex":
 
    foldable-cato-4o3a-aoct-oof6c29596c4
    
and transformed by mpretty() into

    Foldable Cat  
    
using the supplied corpus of readable hex-like scrabble words. 

## The upshot

If you are prepared to wait minutes or hours for your unique identifiers, their hexadecimal hashes can be memorable 
phrases which might play a role in your application.
    
## Mining 

Got nothing better to do? 

    from muid.memorable import mine
    mine()
   
## Terminology 

The set of strings refered to as "readable hex" is defined as the image of uuid strings (i.e. things generated by str(uuid.uuid4()) 
under the map which swaps out characters as follows: (5->s,1->l,7->t,0->o)
   
## For worry warts ... 

You can generate approximately 2.71 quintillion uuid4() before the risk of collision exceeds fifty percent. When using muid the relevant number 
is not the number of uuid's requested, but the number of attempts, which is reported. One would be surprised, to put it mildly, if this proves to be a 
a real issue. One can also provide Memorable.uuid with a different generator, such as one that produces longer random string. 
   
