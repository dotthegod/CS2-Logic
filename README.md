# CS2-Logic
CS2 Entity logic document to people understand

#Inputs and Outputs

You will use inputs and outputs to work on the entites.

## Output

<img width="419" height="164" alt="image" src="https://github.com/user-attachments/assets/e648cc53-f94c-4116-94b9-9caacfad4dce" />

Outputs look like this. 

`My output named`: This is the place you will sellect when your output will be fired. It depends to what is your entity is but `OnUserX` ones is useable at all entites. `OnUserX` outputs can be fired with `FireUserX` input.

`Target entities named`: Is your target entity that you want to input. `!self` fires for the entity itself, `!activator` fires for the who makes this output fire(like if a button pressed by a player and it has this output it the input goes to the player) (it can be different sometimes), `!caller` also works like !activator but prefer !activator if you dont know what you are doing, 

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

# Point entites

I don't really know how to define this entites but chatgpt says this:

Point entities are non-physical objects placed at a single point in the 3D world. They do not have any physical geometry (brushes or models that block movement) and are often used to control gameplay mechanics, visuals, audio, or logic.

They are called “point” entities because they exist at a specific origin point in the map and are usually represented by a small icon in the editor.

We will be using this entites for basics:

-`point_servercommand`

-`point_teleport`

-`point_worldtext`

-`point_soundevent`

## point_servercommand

point_servercommand lets you use console commands via its `Command` input.

## point_teleport

point_teleport lets you teleport entities. Some people use trigger_teleport to teleport something but i like using point_teleport much more. You put this entity to wherever you want entites to be teleport.

I most of the time use `TeleportEntityToCurrentPos` output because it lets you change the parameter to whatever you want to teleport to it.

<img width="641" height="187" alt="image" src="https://github.com/user-attachments/assets/1c7746c6-ed5f-4c47-b188-3db67d3a39dc" />

Like in this screenshot when entity gets `FireUser1` input it teleports `ball1` entity to the position of `point_teleport`.

## point_worldtext

point_worldtext lets you write texts to the world. You can use most of the fonts that avaible in Windows. 

<img width="165" height="117" alt="image" src="https://github.com/user-attachments/assets/b3693a61-a3ff-46ab-a776-b195f480378a" />

## point_soundevent

point_soundevent lets you play sounds in the position of the entity.



# Triggers

<img width="760" height="631" alt="image" src="https://github.com/user-attachments/assets/10e238e2-99c0-461d-8761-42e081bbea66" />

With triggers you can detect:

-If something inside the trigger (trigger_multiple)

-If someone looking to the trigger (trigger_look)

-If you want to damage to someone which inside the trigger (trigger_hurt)

-If you want to push someone in trigger (trigger_push)

-If you want to teleport (trigger_teleport)

(Triggers does not detect other entities than players at start. You need to change it from spawnflag if you want to detect props etc.)

## trigger_multiple

With trigger_multiple you can detect/do:

-If player exitted the trigger

-If player entered the trigger

-If is there any player in trigger when `TouchTest` input fired

-Trigger output for each player inside the trigger when `TouchTest` input fired (Personal favorite)

For the outputs you can use these:

`OnStartTouch`: Output fires when entity touches it.

`OnEndTouch`: Output fires when entity stops touching it.

`OnTouching`: Output fires when `TouchTest` input came and someone inside the trigger.

`OnTouchingEachEntity`: Output fires for each person when `TouchTest` input came.

`OnNotTouching`: Output fires when there is nobody inside trigger when `TouchTest` input came.

## trigger_look

You can detect if player looking at an entity while player inside the trigger.

## trigger_hurt

You can hurt players when they are inside this trigger. (Also if you hurt them negative it heals the player so you can use this also healing trigger)

## trigger_push

You can push entites with this trigger.

## trigger_teleport

You can teleport entities with this trigger. In order to teleport players you need to put info_teleport_destination and link it to `Remote Destination` key in trigger_teleport.

# Filters

I want to mention filters because most of the time you will use them with triggers. You can also use them to test the activator. There is some filters that you can use:

-`filter_activator_class`

-`filter_activator_team`([You need to add it to the base.fgd](https://docs.google.com/document/d/1buKzjP-2com9GcXVxCfyRBi6sDiKmzMoVy9RNbYQqIo/edit?tab=t.0#heading=h.t02h18b93cu9))

-`filter_activator_context`

-`filter_activator_name`

-`filter_activator_model`


## filter_activator_class

filter_activator_class is a filter that lets you filter by the entities class. 

<img width="409" height="30" alt="image" src="https://github.com/user-attachments/assets/9f493f51-0b61-4778-84da-0914d8af99bd" />

## filter_activator_team

filter_activator_team is a filter that lets you filter by the entities team. You can use this to test if activator of something (like a button) is a T or CT. It wont be able to use if you don't add it to base.fgd. [You need to add it to the base.fgd](https://docs.google.com/document/d/1buKzjP-2com9GcXVxCfyRBi6sDiKmzMoVy9RNbYQqIo/edit?tab=t.0#heading=h.t02h18b93cu9)

## filter_activator_context

filter_activator_context is a filter that lets you filter by the if entity has a certain context. I will be explain it a lot at the context part.

## filter_activator_name

filter_activator_name is a filter that lets you filter by the **targetname** of entity. You can't detect player names with this!

<img width="383" height="29" alt="image" src="https://github.com/user-attachments/assets/009c20b3-2c6b-41d5-89e3-ebadcc514fbd" />

## filter_activator_model

filter_activator_model is a filter that lets you filter by the entities model.

# Contexts

Context is like a tag that you give to entity. You can use filter_activator_context to detect contexts of player. I suggest you to watch [this video](https://www.youtube.com/watch?v=2WDP9cbasOY) to understand how it works.

For add context to the entites/players you need to use `AddContext` input. It doesn't shows up at the dropbar but you can use it.

<img width="416" height="169" alt="image" src="https://github.com/user-attachments/assets/fe56eefe-c73c-4f77-8e66-395f04fec647" />

When `FireUser3` input comes to our entity it will add `key` context to the `prop1` entity.

In order to remove this context from the `prop1` we need to use `RemoveContext` input or `ClearContext`

`RemoveContext` <context name> removes the spesific context that you add into the parameter.

<img width="415" height="161" alt="image" src="https://github.com/user-attachments/assets/c3118b84-fae8-45c9-8cbb-58234d808afa" />

`ClearContext` removes all of the contexts that entity has.





