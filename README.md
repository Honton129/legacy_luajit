# Fork from NebulaZorua's Repository
# This library is meant to work on FNF Psych Engine versions prior to 0.7.
# If you need a library to compile those versions, use [superpowers04](https://github.com/superpowers04/linc_luajit/tree/1906c4a96f6bb6df66562b3f24c62f4c5bba14a7) version.

# linc/LuaJIT
Haxe/hxcpp @:native bindings for [LuaJIT](http://luajit.org/).

This is a [linc](http://snowkit.github.io/linc/) library.

---

This library works with the Haxe cpp target only.

---

### Example usage

See test/Test.hx

Be sure to read the Lua documentation  
www.lua.org/manual/5.1/manual.html  

```haxe
import llua.Lua;
import llua.LuaL;
import llua.State;

class Test {
        
    static function main() {

        var lua:State = LuaL.newstate();
        LuaL.openlibs(lua);
        trace("Lua version: " + Lua.version());
        trace("LuaJIT version: " + Lua.versionJIT());

        LuaL.dofile(lua, "script.lua");

        Lua.getglobal(lua, "foo");

        Lua.pushinteger(lua, 1);
        Lua.pushnumber(lua, 2.0);
        Lua.pushstring(lua, "three");

        Lua.pcall(lua, 3, 0, 1);

        Lua.close(lua);
        
    }

}
```
