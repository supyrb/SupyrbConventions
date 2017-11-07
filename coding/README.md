# Coding Conventions
Coding conventions for C# in Unity

## IDE
Windows:
* [Visual Studio Community 2017](https://www.visualstudio.com/vs/community/)
  * [ReSharper](https://www.jetbrains.com/resharper/)
    * [Resharper Settings v0.1](settings/Resharper_SupyrbTeamSettings_v0.1.DotSettings)
    * [Heapview](https://github.com/controlflow/resharper-heapview)
    * [Resharper Unity](https://github.com/JetBrains/resharper-unity)
  * [Spell Checker](https://visualstudiogallery.msdn.microsoft.com/7c8341f1-ebac-40c8-92c2-476db8d523ce)
* [Notepad ++](https://notepad-plus-plus.org)
  * [Shader highlighting theme](https://github.com/JohannesDeml/NotepadPP-SolarizeShaderTheme)

## Naming Conventions
Follow these naming conventions: http://www.dofactory.com/reference/csharp-coding-standards

## Unity specific
* Use [SerializeField] (with a public property if necessary) instead of public fields.
  ```
  [SerializeField] private int someInt = 0;
  ...
  public int SomeInt { get {return someInt; } }
  ```
* Use [Tooltip("")] for commenting fields
  ```
  [Tooltip("Changes the horizontal speed of the player")]
  [SerializeField] private float horizontalSpeed = 2f;
  ```
* Use [Unit("")] to give extra information about the unit of a field
  ```
  [Unit("meters/second")]
  [SerializeField] private float startVelocity = 5f;
  ```
  
* If not explicitly required to have a component use [Reset()](https://docs.unity3d.com/ScriptReference/MonoBehaviour.Reset.html) instead of [[RequireComponent()]](https://docs.unity3d.com/ScriptReference/RequireComponent.html)
* Use [OnValidate()](https://docs.unity3d.com/ScriptReference/MonoBehaviour.OnValidate.html) to precalculate properties
* Pack all editor scripts like Reset(), OnValidate() or other methods only used in the editor at the end of the class and encapsulate them with #if UNITY_EDITOR #endif
  ```
  #if UNITY_EDITOR
  [Button]
  public void SortArray()
  {
    Array.Sort(sortedArray);
  }

  void Reset()
  {
    if(player == null)
    {
      player = GetComponent<Player>();
    }
  }

  void OnValidate()
  {
    reciprocalValue = 1f/value;
  }
  #endif
  ```
