# Speech Recognition in Unity
Speech (Voice) Recognition using Unity3D and C#.

Source Code- https://github.com/Nitinsharma2021/UNIty-Automatic-Speech-Recognition

## Prerequisites
To run the project, you’ll need the following software components:
* Unity3D 6
* Visual Studio 2022+
* Windows 10



## Source Code
We'll be using the KeywordRecognizer class to detect the voice commands:

```
private KeywordRecognizer recognizer;

private void Start()
{
    if (keywords != null)
    {
        recognizer = new KeywordRecognizer(keywords, confidence);
        recognizer.OnPhraseRecognized += Recognizer_OnPhraseRecognized;
        recognizer.Start();
    }
}

private void OnApplicationQuit()
{
    if (recognizer != null && recognizer.IsRunning)
    {
        recognizer.Stop();
    }
}

private void Recognizer_OnPhraseRecognized(PhraseRecognizedEventArgs args)
{
    word = args.text;
    results.text = "You said: <b>" + word + "</b>";
}
```


