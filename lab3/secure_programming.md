# Secure programming

## Software vulerabilities

A software vulnerability  is a weakness an atacker can exploit to obtain advantage.

In the example we can find vulnerabilities: the harcoded password and a potential bufeer overflow.
 ### Code vulnerabilities
- Information leakage:
- Buffer overflow: allocation and deallocation of memory
- Race condition
- Invalid data processing

We have vulnerabilities when we have complexity, when we have changing or incorrect assumpions, when we have poor implementation of software interfaces. Inadeguate knowledge of secure coding practices.


## Secure Programming

We need to use secure programming.

The defender must defend all points, while an attacker can use the wekest point. 

Minimize your attack surface: limit the enable modules, services, and interfaces

We cannot rely on other systems to protect your software, but use defence in depth. Always assume that external systems are insecure.

## Secure Software development

we can't consider secure aspect only when we develop. We need to use security by design methodology.

**threat modelling**: a threat model is a security based analysis aiming at identifying the highest level security risks posed to a product and the way attacks can carried on.

Since the very beginning of the design  phase we need to identify the critical aspects of our application. Then we do threat modelling, nad the outcome of the design phase  should be reviewed by an external team to identify possible issues.

We should, during the test phase, test the behavior of our system when exposed to an attack.

When the software is shipped, the process to react to new vulnerabilities should be defined.