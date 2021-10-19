# AIEnemyDeath

In this tutorial we will be able to shoot enemies and make them dissapear. We will need to follow the next steps:

## 1. Creating a project

Create a new Unity project, call it EnemyDeath or whatever suits you. Add a plane 3D object, a 3D cube called Enemy, an empty game object (called Player) with a cylinder child object attached to it, call this cylinder Gun. Also, attach the MainCamera to the Player.

![image](https://user-images.githubusercontent.com/91539042/137912812-640445fd-037e-415e-84ac-304705658f26.png)

## 2. Target script

Firstly we will create a new script called ``Target``. We will delete ``void Start`` and ``void Update`` since we are not going to use them. Then add a ``public int health`` and set it to 5 (we can adjust the number as we like), this is our enemy's health. 

![image](https://user-images.githubusercontent.com/91539042/137911767-dd302678-76e5-4e6f-be8e-8a5e720ddf3c.png)

We will need to create a ``public void Take Damage(float amount)``, this amount will represent the one stated in the inspector. We will need to add an ``if`` statement that will state if health is smaller or equal to zero, the game object with this script will be destroyed.

![image](https://user-images.githubusercontent.com/91539042/137911384-56d56cd1-8069-4442-a0c5-3d66c7a8d512.png)


We will add a ``public void Damage`` with another ``if`` statement saying when the object takes damage, if health is bigger or equal to 1, it will decrease, if not (if health is smaller than 1) the game object will be destroyed.

![image](https://user-images.githubusercontent.com/91539042/137912380-df7801b8-6d59-49aa-9bbd-aedcaec5430f.png)

Attach this script to the Enemy. In the inspector you will be able to see the public int healt, you are able to change in the inspector as you like.

## 3. Gun script

Add a ``public float damage`` and set it to 1, this is how much damage we want to take when the Enemy is shot. Add a ``public float range`` which will indicate how far we want to shoot. Also, add a ``public Camera cc``, meaning where the raycast will appear. 

![image](https://user-images.githubusercontent.com/91539042/137914991-6337de5a-bb71-4517-9935-94e89d9bdb0a.png)

We can delete the ``void Start`` sinde we do not need it.

In ``void Update`` we will need to add an ``if`` statement that will say that if we click the L mouse button, we will shoot. Unity has this function establishes already, but you might want to check it in Edit -> Project Setting -> InputManager -> Axes, then you should see Fire1 there. Inside the ``if`` function we will writte ``Shoot()``, meaning the shoot function we will appear. We need to create this function.

![image](https://user-images.githubusercontent.com/91539042/137915735-6f2eb352-4eb5-42db-83b7-4319c79e07c8.png)

Create a ``void Shoot()``. Inside, write a ``RaycastHit hit`` which means we will use raycasts to shoot. We will need an ``if`` statement saying if we shoot in the camera position, the raycast will appear in the forward direction when it hits something within its shooting range.
We will need to state ``if`` we hit an item with the tag ``Enemy``, the enemy will receive damage. We also need to mention the ``Target`` to state it will lose health.

![image](https://user-images.githubusercontent.com/91539042/137920343-320fc428-1d71-47b7-83ec-99afa6ae737d.png)


In another ``if`` statement, state if the target is ``null``, nothing happens. The last function we need will be a ``target.TakeDamage(damage)`` stating that in the ``Target`` script, we have a ``TakeDamage`` function, so this function will be activated.

It should look something ike this:

![image](https://user-images.githubusercontent.com/91539042/137920150-dd88a90d-d9a5-4956-aaca-21dc129127e9.png)

You should be a able to make the Enemy dissapear now after hitting it 5 times or depending on the numbers you gave the variables.

