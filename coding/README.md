# Coding Conventions
Coding conventions for C# in Unity

## IDE
Windows:
* [Visual Studio Community 2017](https://www.visualstudio.com/vs/community/)
 * [ReSharper](https://www.jetbrains.com/resharper/)
  * [Resharper Settings v0.1](settings/Resharper_SupyrbTeamSettings_v0.1.DotSettings)
  * [Heapview](https://github.com/controlflow/resharper-heapview)
 * [Spell Checker](https://visualstudiogallery.msdn.microsoft.com/7c8341f1-ebac-40c8-92c2-476db8d523ce)

## Naming Conventions
Follow these naming conventions: http://www.dofactory.com/reference/csharp-coding-standards

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
* If not explicitly required to have a component use [Reset()](https://docs.unity3d.com/ScriptReference/MonoBehaviour.Reset.html) instead of [[RequireComponent()]](https://docs.unity3d.com/ScriptReference/RequireComponent.html)
* Use [OnValidate()](https://docs.unity3d.com/ScriptReference/MonoBehaviour.OnValidate.html) to precalculate properties
* Pack all editor scripts like Reset(), OnValidate() or other methods only used in the editor at the end of the class and encapsulate them with #UnityEditor
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
