
# About

[Unity 5.x Cookbook](https://www.packtpub.com/game-development/unity-5x-cookbook)
by Matt Smith, Chico Queiroz
published by Packt, 2015

# Thoughts

Not a strong book. Some helpful intro to concepts, but the code samples are sloppy. As is typical of Unity community bullshit, references to any sources outside of the Unity ecosystem are scarce.

Below I have also included some stuff not covered in the book (for want of a better home for Unity tips.)

# Take-Aways

* `[SerializeField]` on private properties for Editor only
* `UnityEvent` - excellent way to provide editor-authorable script triggers
* `Application.isWebPlayer`, `Application.absoluteURL`
* `WWW` only supports fetching text data, audio data, and image data
* `PlayerPrefs` supports only string, integer, and float properties
* `Resources.Load()` takes filename without extension
* Resources folder - stand-alone Mac / Win builds only, no web player
* `Path.Combine` is helpful for path delimiter issues between Windows and Mac
* `AudioMixerSnapshot` can be used to build dynamic soundtracks, background noise
* Unity 5 got rid of "quick component property getters" such as .rigidbody and .audio
* `IEnumerator Start()`, `MonoBehaviour.Start` can be a coroutine and `yield return Wait`
* Unity has its own null reference type - operator `==` and `??` behave differently on some types, eg. `Texture`
* `Mathf.Clamp`

## Optimization Tips

* `SendMessage` (reflection) is generally slower than delegates or events
* Job System creates a lot of worker threads, but entities not spawned at the root level (ie. under a common parent transform) must be batched together
* Aggressive Inlining optimization attribute - `[MethodImpl((MethodImplOptions)0x100)]` or `[MethodImpl(MethodImplOptions.AggressiveInlining)]`
* RenderTexture.GetTemporary gets working buffers; GetNativePtr to avoid making a copy
* `GL.IssuePluginEvent()`, `void UnityRenderEvent(int marker)`, `ID3D11DeviceContext::UpdateSubresource()`
* careful with LOD: introducing more levels of LOD can interfere with draw call batching and end up with worse performance
* increasing the delay between `FixedUpdate()` will reduce physics load (free up CPU) at the cost of simulation accuracy

## Gameplay Tips

* `Time.timeScale = 0f` to pause the game
* `Cursor.visible = false` hide mouse cursor
* `Time.fixedDeltaTime` is helpful to keep gameplay systems updating at a consistent rate
* `MonoBehaviour.OnBecameVisible` / Invisible - runs even when in editor
* Scene Panel affects OnBecameVisible - objects visible in scene view are "visible"
* coroutines can spread long calculations over multiple frames; `yield return null` to continue next frame, `yield break` to exit
* Unity Editor logs
** `C:\Users\username\AppData\Local\Unity\Editor\Editor.log`
** `~/Library/Logs/Unity/Editor.log`

## Rendering Tips

* `LineRenderer` is a good component for debug visualization and cheap fx
* `GameObject.CreatePrimitive` can spawn cubes, spheres
* Change object's texture with `GameObject.renderer.material.mainTexture`
* Specular or Metallic materials workflow changes the meaning of Albedo, but Physically Based Shader supercedes this
* `ReflectionProbe` generates runtime Cubemap, used for reflection effects
* `LightProbe` queries light sources for dynamic lighting textures
* Shader/Procedural Skybox for dynamic sky colour, day-night cycle
* Standard Assets Package has some fx including VignetteAndChromaticAberration, NoiseAndGrain
* `MonoBehaviour.OnRenderImage` can be used in combination with `Graphics.Blit` to apply post-effects to a scene
* `Graphics.DrawMeshInstanced` - can stamp meshes into the scene

## Camera Tips

* Off-screen render from `Camera.targetTexture`, eg. mini-map
* Screenshots via `Texture2D.ReadPixels()` and `Apply()`
* Set zoom / field of view by `Camera.main.fieldOfView`
* Set viewport from screen space by `Camera.pixelRect`

## Animation Tips

* update a bone in `LateUpdate()` so that it happens after the animation controller
* Mechanim states have root motion "handled by script" option that lets controller script control movement
* Instantiate and collision trigger with a target bone to spawn a prop (equipment, arrow, etc.) as a child object on a character
* Animation Events allow timelines to trigger script functions
* Simple Ragdoll recipe
** disable CharacterController, BasicController, and Animator components
** enable Collider and CharacterJoint component on each bone
** for each bone's Rigidbody, turn isKinematic off and detectCollisions on
* Rigidbody.addExplosionForce
* procedural mouse aim animation using a spine transform and localEulerAngles
* Navigation -> Object -> Navigation Static checkbox
* can tie Animator.speed to AudioSource.pitch

## UI Tips

* UI anchors all on one point means no stretching occurs
* To render UI in world space, change Canvas render mode
* Image.sprite - swap a UI sprite
* Collider2D.CompareTag() - check hit by entity type
* Button transition type "Animation" provides keyframe timeline
* Bump UI sprites to front with RectTransform.SetAsLastSibling()
* Text fields support some markup with Rich Text setting
* TextMesh is convenient for 3D text
* SliderValueToText - display slider value
* Hide slider handle to make it display-only
* Use GameObject tags to identify minimap blipped entities
* SetCustomCursor with Texture2D
* ToggleGroup - Toggles as radio buttons
* Tiled image much cheaper than a grid of sprites
* GUILayout.Label() can take a Sprite to draw an editor icon
* EditorUtility.DisplayProgressBar / ClearProgressBar

## Pixel Perfect Settings

* Project Settings: Disable Anti-Aliasing
** Edit -> Project Settings -> Quality
*** Anti-Aliasing -> Disabled
* Sprite Import Settings: Filter Mode = Point, disable compression
** select sprite / texture asset
*** Filter Mode -> Point (no filter)
*** Compression -> None
* Pixels Per Unit (PPU)
*** recommended to set it to your tile size
* Camera Orthographic Size
** should be set to = Vertical Screen Resolution / (PPU * 0.5)
*** eg. 270 / (16 / 2) = 8.4375
** Snapping to Pixel Grid
*** child object containing the sprite renderer
*** Late Update ()
*** position.x = (Mathf.Round(parent.position.x * PPU) / PPU) - parent.position.x;
*** position.y = (Mathf.Round(parent.position.y * PPU) / PPU) - parent.position.y;

# Concepts

* Albedo - diffuse colour of material
* Animation Layers, Avatar Masks - animations target specific bones, blending
* Animation State Machine, Animation Clip
* Audio Reverb Zone
* Audio Source, Audio Listener, Audio Mixer components
* C# Extension Class - eg. add methods to Rect
* Craig Raynolds - Steering Behaviors For Autonomous Characters
* Craig Reynolds - seek algortihm, boids, flocking
* Draw Call Batching - static and dynamic batching
* Ducking / Duck Volume - lower musical score to emphasize a sound effect
* Frame Debugger - see how a frame was rendered
* GameObject tags - categorize entities
* GPU Instancing
* MonoBehaviour.OnDrawGizmos()
* NavMeshAgent component
* Physically Based Shader - new shader system
* Resources folder, WWW class, PlayerPrefs
* Root Motion - Mecanim can apply animated movement to actor position
* Specular / Smoothness - shininess of material
* Specular vs Metallic materials workflow
* Utility.Md5Sum

# Techs

* Bitmap2Material (material editor)
* Fungus (state machine)
* Fuse & Autorigger (Mixamo animation tools)
* Mecanim (animation controller)
* Mudbox (material editor)
* Substance Painter (Allegorithmic, material editor)
* zBrush (material editor)

# Code Clips

`Vector3 localUp = transform.TransformDireciton(0f, 1f, 0f);`

`List<T>.Sort(delegate(T a, T b) { return T.Compare(a, b); });`

```
public static Quaternion QuaternionFromMatrix(Matrix4x4 m)
{
return Quaternion.LookRotation(m.GetColumn(2), m.GetColumn(1));
}

public static Vector4 PositionFromMatrix(Matrix4x4 m)
{
	return m.GetColumn(3);
}
```

```
IEnumerator RequestImage()
{
	var request = new WWW(url);
	yield return request;
	Texture2D result = request.texture;
}
```

```
// Texture2D to Sprite
var pivot = new Vector2(0.5f, 0.5f);
Sprite result = Sprite.Create(texture,
	new Rect(0, 0, texture.width, texture.height),
	pivot);
```

```
IEnumerator SaveScreenshot()
{
	yield return new WaitForEndOfFrame();

	var texture = new Texture2D(Screen.width, Screen.height, TextureFormat.RGB24, false);
	texture.ReadPixels(new Rect(Screen.width, Screen.height, 0, 0), 0, 0);
	texture.Apply();

	byte[] bytes = texture.EncodeToJPG(jpgQuality); // or EncodeToPNG()
	File.WriteAllBytes(Application.dataPath + "/../" + prefix + date + format, bytes);
	Destroy(texture);
}
```

# Articles

* https://www.allegorithmic.com/pbr-guide
* https://www.slideshare.net/RenaldasZioma/unite2014-mastering-physically-based-shading-in-unity-5
* http://aras-p.info/texts/files/201403-GDC_UnityPhysicallyBasedShading_notes.pdf
