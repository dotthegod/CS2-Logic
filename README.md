<img width="419" height="164" alt="image" src="https://github.com/user-attachments/assets/df9e40c2-68d7-4f29-b023-5d95f121b949" /># CS2-Logic
CS2 Entity logic document to people understand

#Inputs and Outputs

You will use inputs and outputs to work on the entites.

## Output

<img width="419" height="164" alt="image" src="https://github.com/user-attachments/assets/e648cc53-f94c-4116-94b9-9caacfad4dce" />

Outputs look like this. 

`My output named`: This is the place you will sellect when your output will be fired. It depends to what is your entity is but `OnUserX` ones is useable at all entites. `OnUserX` outputs can be fired with `FireUserX` input.

`Target entities named`: Is your target entity that you want to input. `!self` fires for the entity itself, `!activator` fires for the who makes this output fire(like if a button pressed by a player and it has this output it the input goes to the player) (it can be different sometimes)

`Via this input`: Is what do you want that entity to do. It depends on the your target entity.

`With a parameter override of`: When you use some inputs you need to use a parameter to change at the target entity.

`After the delay of`: Is the amount of time for it to fire this output.(PSA: If you use 0.01 and rapidly use that output it wont be fired 100 at 1 second. IIRC it fires 66 per second)

`Fire once only`: This checkbox makes the output fired once in every **round**


# Logic Entites
There is bunch of logic entites out there but we will use few of them:

-`logic_auto`

-`logic_case`

-`logic_compare`

-`logic_relay`

-`logic_eventlistener`

## logic_auto

logic_auto is a logic entity that does its job auto. We most of the time use it with the `OnMapSpawn` output with `point_servercommand` entity to set console commands for our maps (you can also add it to your maps cfg). `OnMapSpawn` output fires once every round. So you can use it however you need.

## logic_case

logic_case is a logic entity that you can use to trigger various outputs from it.

<img width="206" height="105" alt="image" src="https://github.com/user-attachments/assets/8d1da3b3-5ec2-4f51-9471-f6da61a042b0" />

It has a randomizing feature which we can use to get random outputs.

I will be telling more about logic_case later on the document.

## logic_compare

logic_compare is a logic entity that lets you compare values. It can be useful with point systems.

I will be telling more about logic_compare later on the document.

## logic_relay

logic_relay is like a packet of outputs. If you are similar with coding you can think this as `functions`. If you want some entites to fire same output you can use `logic_relay`

## logic_eventlistener

logic_eventlistener is a logic entity that listens events that happen in the game like anyone dead or shots fired.

!! IT CAN'T LISTEN ANYONE SPESIFIC AND USE AS !activator !!

You can find events that you can use in [this website](https://wiki.alliedmods.net/Counter-Strike:_Global_Offensive_Events).

(I'm not really sure if all of these work)
