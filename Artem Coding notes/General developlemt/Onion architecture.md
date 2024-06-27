![[layers levels.png]]

> [!Long rant]
> So you have level 1 which is Presentation and Infra, level 2 is Application and level 3 is Core (pretend it's not written Domain lol).
> 
> - A level cannot depend on another level if it's lower than itself. Infra can depend on Application and Core for example, but Application can only depend on Core.
>     
> - Everything should be at the lowest level possible, so your repository implementation shouldn't go past level 1 but its interface will. This is why Core tends to be the cleanest.
>     
> - Level 1 is the only one that can communicate with the external world either by receiving requests or initiating them. So your Presentation might receive requests from the browser and your Infra might initiate requests to the DB. The Infra can also receive a request from a message bus for example, there are no restrictions which can do what.
>     
> - Everything that happens in your system will tend to go from lowest to highest to lowest. So an insert will go: Level 1 (Controller receives request) -> Level 2 (Application validates business rules) -> Level 3 (Core holds the data in the entity) -> Level 2 (Application asks data to be stored) -> Level 1 (Infra calls the DB to store data). Think of it as a drill going to the center of the circle and then back out on the other side.
>     
> - Don't try to memorize where stuff goes. Follow the rules and find out. Why is EmailService at Infra? Because that's the lowest level that needs it. But why is IEmailService at Application? Because a business rule might need to send an email.
>     
> 
> IMO these layers shouldn't be fixed but the rules are. Want to split your Infra into DB and External services? Fuck it, do it, now you have 3 layers at level 1. Want to introduce a Domain services layer between Application and Core? Cool, now you have 4 levels. You can mess around with this but ultimately they will always follow those rules.

> [!Dismissive answer]
> I've been a developer and architect for over 25 years. This shit comes and goes. I couldn't tell you half of the latest "patterns" because I honestly don't care. There's only one pattern I will always follow...KISS. Keep it simple stupid. You don't need to follow some new pattern that adds all kinds of complexity to code that can be done in a simple, understandable way just because somebody says you should. Been there, done that and KISS always wins.

[reddit discusion](https://www.reddit.com/r/dotnet/comments/1doiovz/trying_to_wrap_my_head_around_clean_architecture/) 
[Understanding Onion Architecture: An Example Folder Structure](https://medium.com/@alessandro.traversi/understanding-onion-architecture-an-example-folder-structure-9c62208cc97d)

[Clean onion vs  Vertical Slice Architecture for Enterprise Apps](https://www.reddit.com/r/dotnet/comments/lw13r2/choosing_between_using_cleanonion_or_vertical/)