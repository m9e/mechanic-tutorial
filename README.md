# mechanic-tutorial
An extended example for building a REST web service with mechanic

[Mechanic](https://github.com/factioninc/mechanic) is a code generation tool which consumes [OpenAPI 3.0](https://www.openapis.org/) specifications and produces scaffolding to rapidly build REST web services. It is written in and for python and leverages Flask, Marshmallow, and SQLAlchemy.

## The problem with most code generation tools

The problem with most code generation tools is that they are designed to only be used once. They are helpers or scaffolders, but they are not meant to be part of an iterative development process. So you can create a "Pet" API specification, and use a tool like swagger-codegen, but once you've generated code you see blocks that contain things like

```
# Do magic!
```

And when you've replaced the `# Do magic!` with something useful, if you should ever modify the specification and want to run it again, you will overwrite anything modified.

## Diving in

Start with a new virtualenv:

```ShellSession
astrolabe:code matt$ virtualenv -p python3 mechanic-example
Running virtualenv with interpreter /Library/Frameworks/Python.framework/Versions/3.6/bin/python3
Using base prefix '/Library/Frameworks/Python.framework/Versions/3.6'
New python executable in /Users/matt/code/mechanic-example/bin/python3
Also creating executable in /Users/matt/code/mechanic-example/bin/python
Installing setuptools, pip, wheel...done.
astrolabe:code matt$ cd mechanic-example/
astrolabe:mechanic-example matt$ source bin/activate
(mechanic-example) astrolabe:mechanic-example matt$
```

