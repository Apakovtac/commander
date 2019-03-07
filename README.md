# Commander
**Note**: This is meant to be a proof of concept for Lunar's usability!

We have taken advantage of the following Lunar features (at the time of writing)

 - [x] Classes
 - [x] [Class Inheritance](https://github.com/Apakovtac/commander/blob/ebbafb1b24faa49d90381749a79f5074f563e2d0/Commander/Lexer.lunar#L35)
 - [x] [Static methods](https://github.com/Apakovtac/commander/blob/ebbafb1b24faa49d90381749a79f5074f563e2d0/Commander/PlayerUtils.lunar#L26)
 - [x] [Lambda expressions](https://github.com/Apakovtac/commander/blob/ebbafb1b24faa49d90381749a79f5074f563e2d0/Commander/PlayerUtils.lunar#L28-L32)
 - [x] [Self-assignment operators](https://github.com/Apakovtac/commander/blob/ebbafb1b24faa49d90381749a79f5074f563e2d0/Commander/Lexer.lunar#L98) (only `..=` was used in this project)

## Syntax
The `Lexer` class attempts to group your message based on its syntax. If you write `"hello world"`, you get back `hello world` as one single object.

By default, we have a `@` prefix which signals to Commander that your message invokes a command.

The first object is the alias, which can be in the following format: `test` or `"hello world"`, both of which is one alias.

Although every arguments in Commander is an array of objects, we support multiple objects in one single argument, which takes the syntax: `one, two, three, four`. This is all one argument that has four objects. So with `@teleport one, two, "player three", four me`, its first object: `teleport`, first argument is an object which is an array of objects: `one, two, "player three", four`, and second argument is one object: `me`.

### Examples
So these are valid commands for Commander: `@kill others`, `@"send message" random "hehe lol"`, `@teleport one, two, "player three", four me`.
