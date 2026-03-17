---
id: argument form
aliases: []
tags: []
---
# Argument form


An **argument form** is a sequence of [[statement form]]. In an argument form
all statement are called the **premises** (or **assumptions** or **hypotheses**)
except for the final one which is called the **conclusion**

## Valid and invalid arguments

An argument form is **valid** when no matter what particular statements are
subsituted for the statement variables in its premisesif the resulting premises
are all true then the conclusion is also true

An [[argument]] is **valid** when its form is **valid**

### Testing an argument form

Here is the procedure for testing an argument form

1. Identify the premises and conclusion of the argument form
2. Construct a truth table showing the truth values of all the premises and the
   conclusion
3. A row of the truth table in which all the premises are true is called a
   **critical row**. If there is a critical row in which the conclusion is false
   then it is possible for an argument of the fiven form to have true premises
    and a false conclusion and so the argument form is valid. If the conclusion in
    every critical row is true then the argument form is valid

## Modus ponens and Modus tollens

An argument form consisting of two premises and a conclusion is called a
**syllogism**

The first and second premises are called the **major premise** and **minor
premises

### Modus ponens

The **modus ponens** is the most famous form of syllogism. It has the following
form 

$$
if \ p \ then \ q
$$
$$
p
$$
$$
\therefore q
$$

### Modus tollens

The **modus tollens**  is also another valid argument form. It has the following
form


$$
if \ p \ then \ q
$$
$$
\neg p
$$
$$
\therefore \neg q
$$

## Rule of inference

A **rule of inference** is a form of argument that is valid. Modus ponens and
modus tollens are both rules of inference

Here is other valid argument form

### Generalization

**Generalization** is an argument form that is valid. It has the following
form

1.

$$
p
$$
$$
\therefore p \lor q
$$

2.

$$
q
$$
$$
\therefore p \lor q
$$

### Specialization

These argument forms are used for specializing. When classifying objects
according to some property. We often know much more about them than wheter they
do or do not have that property. When this happens we discard extraneous
information as we concentrate on the particular property of interest

1.

$$
p \land q
$$
$$
\therefore p
$$

2.

$$
p \land q
$$
$$
\therefore q
$$

### Elimination

These argument forms say that when you have only two possibilites and you can
rule one out the other must be the case

1.

$$
p \lor q
$$
$$
\neg q
$$
$$
\therefore p
$$

2.

$$
p \lor q
$$
$$
\neg p
$$
$$
\therefore q
$$

### Transitivity

Many arguments in mathematics contain chain of if-then statements. From the fact
that one sttement implies a second and the second implies a third. We can
conclude that the first statement implies the third

Transitivity follow this forms

$$
p \implies q
$$
$$
q \implies r
$$
$$
\therefore p \implies r
$$

### Proof by division into cases

Proof by division into cases is an argument form that we use we know one thing
or another is true. If we can show that in either case a certain conclusion
follows then this conclusion must also be true

It follows this form

$$
p \lor q
$$
$$
p \implies r
$$
$$
q \implies r
$$
$$
\therefore r
$$
