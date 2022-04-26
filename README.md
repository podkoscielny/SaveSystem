# SaveSystem
Easy to use SaveSystem for Unity 

## Setup Guide

### Installation
  Download the zip file and place SaveSystem.cs script in your project.
  
### Usage
Only those types that are serializable can be saved. Make sure to include `using AoOkami.SaveLoadSystem;` in your scripts.
SaveSystem class is static so you can easily access it anywhere in your code. Each method takes string savePath argument which leads to location where you want to save
your data. SaveSystem adds that path to Application.persistentDataPath and uses _.save_ extension for save files.
  
### Methods

#### _void_ Save\<T>(_string path, T data_)
Example usage:

```csharp
using AoOkami.SaveLoadSystem;

private const string SAVE_PATH = "example/file_name";

private void SaveData() => SaveSystem.Save<float>(SAVE_PATH, 1);
```


#### _T_ Load\<T>(_string path_)
Example usage:

```csharp
using AoOkami.SaveLoadSystem;

private CustomStruct _customStruct;
private const string SAVE_PATH = "example/file_name";

private void Start() => _customStruct = SaveSystem.Load<CustomStruct>(SAVE_PATH);
```

#### _void_ DeleteSaveFile(_string path_)
Example usage:

```csharp
using AoOkami.SaveLoadSystem;

private const string SAVE_PATH = "example/file_name";

private void Start() => SaveSystem.DeleteSaveFile(SAVE_PATH);
```
