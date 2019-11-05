# Events

Here's a list of all Events currently in latest version of Gameplay Ingredients.

| Name                    | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| OnAwakeEvent            | Triggers when the Game Object becomes Awake (Called upon the `void Awake()` Message) |
| OnButtonDownEvent       | Triggers when an Input button is hit (Old Input System)      |
| OnColliderEvent         | Triggers when a collision between Colliders happens or is released |
| OnDestroyEvent          | Triggers when a Game Object is being destroyed.              |
| OnEnableDisableEvent    | Triggers when a Game Object becomes enabled or disabled.     |
| OnGameManagerLevelStart | Triggers when the GameManager sents its Level Start (Sent as sync point after all levels are loaded and started) |
| OnJointBreakEvent       | Triggers when a RigidBody Joint constraint breaks.           |
| OnKeyDownEvent          | Triggers when a Keyboard Key is Pressed or Released          |
| OnMessageEvent          | Triggers when the Messager broadcasts a given Message        |
| OnMouseDownEvent        | Triggers when the owner's collider becomes clicked by the mouse (or mouse released) |
| OnMouseHoverEvent       | Triggers when the owner's collider becomes hovered in/out by the mouse |
| OnStartEvent            | Triggers when the `void Start()` unity message is sent to the object. |
| OnTriggerEvent          | Triggers when the trigger collider is entered or exited by another object. |
| OnUpdateEvent           | Triggers when the `void Update()` unity message is sent to the object.  **Performance intensive, Use with caution** |
| OnVisibilityEvent       | Triggers when the owner game object becomes visible or hidden. |

