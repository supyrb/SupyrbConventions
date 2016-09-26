# Coding Conventions
Coding conventions for C# in Unity

## IDE
Our unity projects are written in C#. Get an IDE you can work with. General recommendations:
* [Visual Studio Community for Windows](https://www.visualstudio.com/vs/community/)
 * [ReSharper](https://www.jetbrains.com/resharper/)
 * [Visual Studio for Unity](https://visualstudiogallery.msdn.microsoft.com/8d26236e-4a64-4d64-8486-7df95156aba9)
 * [Spell Checker](https://visualstudiogallery.msdn.microsoft.com/7c8341f1-ebac-40c8-92c2-476db8d523ce)
 * [Shader Unity Support](https://visualstudiogallery.msdn.microsoft.com/ed812631-a7d3-4ca3-9f84-7efb240c7bb5)
* [Monodevelop for Mac](http://www.monodevelop.com/)

## Naming Conventions
We follow these naming conventions: http://www.dofactory.com/reference/csharp-coding-standards

## Unity specific
* Use [SerializeField] (with a public property if necessary) instead of public fields.
* Use [Tooltip("")] for commenting fields

  ```
  // Use Tooltips for commenting exposed fields
  [Tooltip("This int can have a default value." +
  "It also won't be set on accident in the game other than by the class itself.")]
  [SerializeField] private int someInt = 0;
  ...
  public int SomeInt { get {return someInt; } }
  ```
* For complex configurations create four [Serializable] classes with the group naming:
 * *Configuration variables* are tweakable values variables about the initial state and behaviour of the object
 * *State variables* contain information about the state the object is in right now. Those values can be exposed for debugging reasons. If they are exposed an debugging variable read the states has to be established
 * *Bookkeeping variables* contain information about past states, something like counters or time information
 * *Connector variables* connect this object with other assets and scripts like the rigidbody or a text
