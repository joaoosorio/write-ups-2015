# Boston Key Party CTF 2015: symphony

**Category:** 
**Points:** 
**Solves** 
**Description:**

> A less than four characters number, bigger than 999?Maybe the bug is elsewhere. : 25

## Write-up

O php nao é type safe. Se tivermos por exemplo uma string $x = "2e8", e compararmos essa string com um numero, como é feito no server, $x > 999, o php vai neste caso interpretar a string como um numero em notacao cientifica, ou seja $x == 2 x 10^8 , que obviamente passa no teste.

## Other write-ups and resources

* none yet
