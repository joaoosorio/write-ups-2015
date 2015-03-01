# Boston Key Party CTF 2015: museum-of-fine-arts

**Category:** 
**Points:** 
**Solves** 
**Description:**

> Because cryptography is hard, we only implemented a hand-made PRNG. What could possibly go wrong? : 25

## Write-up

O codigo inicializa o PRNG com a funcao microseconds(). A partir dai o PRNG debita sempre a mesma sequencia. Por isso basta saber qual o valor da funcao microseconds(). A maneira mais simples é fazer um brute force attack:  

    $v0=12079392      // primeiro valor dado pelo server
    $r=0;         
    $t=microtime();   // microtime actual
    while ($r!=$v0){  
    	mt_srand(($t ^ rand(1, 10000)) % rand(1, 10000) + rand(1, 10000));  // init PRNG
    	$r = mt_rand (0, 0xffffff);  // primeiro valor do PRNG
    	$t--;  // brute force t ate o primeiro valor do PRNG ser igual ao do server                     
    }  
    print 'v0='.$r.'<br>';  
    for ($i=1; $i<4; $i++)  
    	print 'v'.$i.'='.mt_rand(0, 0xffffff).'<br>';  // v3 é a resposta

## Other write-ups and resources

* none yet
