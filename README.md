# ExplodingLaserShootingBees [![Java CI](https://github.com/Strokkur424/ExplodingLaserShootingBees/actions/workflows/build.yml/badge.svg)](https://github.com/Strokkur424/ExplodingLaserShootingBees/actions/workflows/build.yml)

Have **you** 🫵 ever thought 🤔 that **Bees 🐝 are boring**???? Not with
**ExplodingLaserShootingBees** 🔫!! Witness ✨ ***unparralleled*** performance
thanks to writing the plugin **fully in JVM bytecode** 🏎️🏎️🏎️. As we all know,
assemblers are **faster than compilers** 👍💖. Give it a try **now** 👮‍♀️.

## Features ✨
- All bees 🐝 now explode if you get closer than 2 blocks ⚔️.
- Bees 🅱️ fire **deadly lasers** 🔫 if you come closed than 20 blocks 🐍.

## Download it now!!! 🧆
- Hangar
- Modrinth

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

<br>

## Okay seriously, what the fuck is this?
This is a proof-of-concept plugin written entirely in JASM, a JVM bytecode assembler. Instead of using the nice
and simple Java syntax, you instead directly write JVM instructions.

For this in specific, I am using [jumanji144's Jasm](https://github.com/jumanji144/Jasm) tool. With it I am compiling
all `.jasm` files into `.class` files, which are then packaged into a normal plugin `.jar`. It's like using Gradle,
except without all the benefits.

### Example?
In Java, you could write the following helper static method to retrieve your plugin instance:
```java
public static ExplodingLaserShootingBees getInstance() {
    return JavaPlugin.getPlugin(ExplodingLaserShootingBees.class);
}
```

In JASM, you have to operate on the stack and call methods via their signatures directly:
```rust
.method public static getInstance ()Lnet/strokkur/explodinglasershootingbees/ExplodingLaserShootingBees; {
    code: {
        ldc Lnet/strokkur/explodinglasershootingbees/ExplodingLaserShootingBees;
        invokestatic org/bukkit/plugin/java/JavaPlugin.getPlugin (Ljava/lang/Class;)Lorg/bukkit/plugin/java/JavaPlugin;
        checkcast Lnet/strokkur/explodinglasershootingbees/ExplodingLaserShootingBees;
        areturn
    }
}
```

### Do you recommend people to actually use JASM for plugins?
No.

### Why?
It took me about 12 hours (and maybe a bit more) to finish this project. I did learn a lot about how the JVM operates
and how the stack in the JVM operates, which was definitely worth it. But making any kind of plugin slightly more complex
than this just takes exponentially longer, because the assembler does not catch issues as well as the Java compiler does.
A lot of time went into spinning up a dev server and then getting yelled at by the JVM that I mistyped a method signature.

**Seriously it is not worth it**.