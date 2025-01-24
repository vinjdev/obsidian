21/08/24 19:32
Fag: [[IIKG2001]] [[CSSLP]]
Tags: [[NTNU]]
___

# Domain 1
Core conecepts
- cia triad
- authentications and authorizations
- accounting
- nonrepudiation


# Holistic security
multiple dimmension

security is in everything
- only secure as the weakest link

![[Pasted image 20240826215419.png]]

# Implementations challenges
Implementing security can be hard. Three main reasons:
![[Pasted image 20240826215703.png]]

## Iron Triangle Constraints
Exploiter takes one weakness
while defender expected to play vigilante 24/7
![[Pasted image 20240826220024.png]]
It defines the constrains of a project. There are constrinas that makes it hard to prioritze securtity
## Security as an afterthought
Security becomes a "add on" activity. And is not properly incoorporated in the project.

## Security vs Usability
Security can rendering the software and its devlopment process

We can make authorizations very good. But it would become troublsome for a consumer to use the program

# Quality and Security
quality assurance = software is reliable, meets standards
The presence of security functionality - not implying the software is secure. 

## security profile what makes software secure
security conecpts are important throughout all of development life cycle
![[Pasted image 20240828133757.png]]
These are security concepts that should be incoorpetaed into the development processs

# Core security concepts
## confidentiality
your info should not be accesable by anyone else
- protections against *unathourized informations disclosure*

## Integrity
protection against improper data *alerations/modification*
data should not be *alterd* without authorization

data should be:
- transmitted processed and stored
- software should perform reliably as intended

## Availability
access of software or the data or information it handles
- downtime is minimized
- The *who* and the *when*
- only by the authorized

## Authentication
information only avalibe for entities that are *valid*
- are you whom you claim to be
ID = three factors - called credentials
- *knowledge*
- *Ownership*
- *Characteristic*
## Authorization
Validations does NOT equal to access to all resources
authorizations = access to objects BASED on rights and privileges

do not *authorize* BEFORE *authenticate*

## accountability and non repudiation
logged and tracked
build history
*non repudiation* - a user cannot deny having made a transaction. sinc history
*auditing* - detective control - view history to find who has taken control
challenges with auditing
![[Pasted image 20240902100105.png]]
# Design Security Concepts
concepts during design and architecting at a definitional level.

### Least privilage
minimum acces right

### Seperation of durties
two or more condition to be met. Before completing a SINGLE task

### Defense in depth or layered Defense
multiple layeres of security safeguards

### fail secure
maintain cia triad. by defaulting to a secure state

### Economy of mechanisms
Keep it simple. Easier to incooparate software security

### Complete Mediation
Checking authorization

### Open design
design should b independent of the design itself. And not the security

### Least common Mechanisms
Diswallows sharing mechanisms that are common to more than one user

### Psychological acceptability
Easy to use and transparent for the user

### Weakest link
Resiliance of software is as STRONG As THE WEAKEST LINK.

### Leveraging existing components
try and not reuse existing code and functionality




# Risk management
about:
preliminary, need of security control, identification, development, testing, implmentation and verification of security control

balance between IT assets and cost of security

common terms:
### Asset
value to the origanization
Data = most important tangible asset


### vulnerability
the weakness or flaw, that an attacker can exploit

### Threat
vulnerability pose a threat. threat is something unwanted event that could occur

### Threat source
anyone with potential to harm

### attack
the activity done by threat agent to inteolally harm

### Probaility
the likelihood of threat to happen

### Impact
outcome of a materilized threat

### Exposure factor
Oppertunity for a threat to cause a loss

### Control


# Summary




# Review Questions



# Referanse
CSSLP domain 1
