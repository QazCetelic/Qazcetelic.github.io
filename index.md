## Hi, I'm Qaz, and these are my projects!

### [SemVer-KMP](https://github.com/QazCetelic/SemVer-KMP)
I needed a SemVer library for a Kotlin project but all of them were JVM only, 
weren't idiomatic Kotlin and didn't have the features that I wanted so I decided to make my own one.
```kotlin
val semver = SemVer("1.0.0")
val semverRange = Semver("0.5.0")..Semver("2.0.0")

println(semver in semverRange) // prints true
println(SemVer("0.5.0-alpha").isPreRelease) // prints true
```

### [CreateNewCreateNew](https://github.com/QazCetelic/CreateNewCreateNew)
I wanted to add a few new entries to the "Create New" file menu in [KDE Plasma](https://kde.org/plasma-desktop/), this had to be done manually, so I decided I should automate it…

![XKCD Automation](https://imgs.xkcd.com/comics/automation.png)

…well this video shows the result.

[![Thumbnail](https://i.imgur.com/5MCRanx.png)](http://www.youtube.com/watch?v=sksK3e-YnUk "Example Video")

### [StarUML™ Watermark Removal 🧹](https://github.com/QazCetelic/StarUML-Watermark-Removal)
A tool for removing watermarks in SVG files created by the StarUML software.

| Before | After |
|    -   |   -   |
| ![WithWatermark](https://user-images.githubusercontent.com/51381523/142168505-f81c183f-e824-41c7-8783-b67dae1f83f9.png) | ![WithoutWatermark](https://user-images.githubusercontent.com/51381523/142168508-7f94454b-0067-42df-b47d-ae98ca70700e.png) |

### [**K**otlin **O**perating **S**ystem **I**nfo](https://github.com/QazCetelic/Kosi)
A capable library for adding specific logic for certain operating systems with varying levels of specificity that uses inheritance and auto-casting to access properties.
```kotlin
fun main() {
    when (val os = currentOS()) {
        is Linux -> {
            println("Tux")
            with(os.distro) {
                println(name)
                println(version)
            }
        }
        is NetBSD -> {
            println("Is this even used anymore?")
        }
        is BSD -> {
            println("This might be FreeBSD")
        }
        is Windows10 -> {
            println("This is a modern version of Windows")
        }
        is Windows -> {
            println("This could be Windows 8 or 7 but also something ancient like ME")
            if (os is WindowsME) println("It actually is")
        }
    }
}
```