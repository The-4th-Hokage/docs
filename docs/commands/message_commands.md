---
title: Message Commands List
tags:
  - commands
  - message commands
---

<style>
    article{
        font-family: monospace;
        padding: 0 3px;
    }
</style>
List of all `message commands` available in the bot.

    The prefix for the bot is ) or m! or minato
    i.e. either of following would work
    )help
    m!help
    minato help
    
    Also by mentioning Minato you invoke commands i.e.
    @{{bot_name}} help

    And in DM's only m! works i.e. only m!help in DM's


    Use ")help command" for more info on a command.
    Use ")help category" for more info on a category.
    Use the dropdown menu below to select a category.

    Support Server
    For more help, consider joining the official server over at https://discord.gg/{{discord_invite_code}}
    
    How do I use this bot?
    Reading the bot signature is pretty simple.
    
    <argument>
    This means the argument is required.
    
    [argument]
    This means the argument is optional.
    
    [A|B]
    This means that it can be either A or B.
    

    [argument...]
    This means you can have multiple arguments.
    
    Now that you know the basics, it should be noted that...
    You do not type in the brackets!


{% for i in commands %}
## {{i.name}}
{% if i.description %}
{{i.description}}
{% endif %}

{% for j in i.commands_list %}
### - {{ j.name }}

{% if j.parent is not none %}
> Parent: [{{j.parent}}](#{{j.parent}})
{% endif %}

{{ j.short_doc }}

{% if j.params %}
    Parameters Required: {{j.params}}
{% endif %}
{% if j.usage %}
    Usage: [prefix]{% if j.parent is not none %}{{j.parent}} {% endif %}{{ j.name }} {{j.usage}}
{% endif %}
{% if j.aliases %}
    Aliases: {{j.aliases}}
{% endif %}

<hr/>
{% endfor %}

<hr/>
{% endfor %}


