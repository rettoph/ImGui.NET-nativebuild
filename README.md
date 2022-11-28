# To Update to the latest cimgui version

git submodule update --init

git submodule update --remote

and then git commit + push.


# To Trigger a release push a tag as shown below

git tag -a v1.4 -m "my version 1.4"

git push origin v1.4

# What is this fork for

Forked from [ImGui.NET-nativebuild tag v1.88](https://github.com/mellinoe/ImGui.NET-nativebuild/tree/9acdb4b2445001f56f3c9400d33541ea57afd73e)


Adds cimplot for 
[ImGui.NET tag v1.88_2](https://github.com/mellinoe/ImGui.NET/tree/421efe7629b92bcc68dcc760716d25ee83d1d461)

Currently used by [Guppy.MonoGame.UI](https://github.com/rettoph/Guppy/tree/master/src/Guppy.MonoGame.UI)

To Update: Ensure the tag versions matches desired tag/version then pull matching cimplot & implot submodules.