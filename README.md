## Protfolio Rehab  :bowtie: ..

> HOWDY! I'm Rehab.
> https://www.linkedin.com/in/rehabalsuliman/

###### This is page of all my work done in *GAME CHANGERS Program*. 
###### I have worked in muliple projects: some projects with team and, some an individual.

### The Projects WITH TEAM and my Roles:

THE PROJECTS | ROLES         
------------ | ------------
**CRAZY HOP**  | **GAME DIRECTOR**, **PROGRAMMER** AND, **TESTER**.
**BUCK BASH**  | ACTUALLY I HAVE JOINED WITH PUCK BASH TEAM AS A **TESTER**, ALSO I HAVE HELPED THEM WITH SOLVE THE BUGS AS A **SUPPORT PROGRAMMER**.
**ALL THE WAY UP** | **TEACH LEAD**, **PROGRAMMER** AND, **PRODUCER**. 
**MAKE ME ANGRY** | WE ARE STILL WORKING ME AND [https://github.com/Bushra-Alghamdi] ON IT, AND WE ARE **PROGRAMMER**, **GAME DIRECTOR**, **TESTER**.


### THE GAMES.
1. **CRAZY HOP**

<img width="337" alt="CRAZYHOPUI" src="https://user-images.githubusercontent.com/68170119/148302351-7969d886-8488-4589-89a9-4a51280dbbf1.PNG">


**here some of my code I have wrote in *CRAZY HOP* for instantiate the platform randomly**.

   void Update()
    {
        int x = Random.Range(0.1f, 1.0f) < 0.5f ? 1 : -1;
        
        CurrentPosition = PreviousPosition + new Vector3((float)x,1,0);

        if(CurrentPosition.x > 3) CurrentPosition.x = 3;
        if(CurrentPosition.x < -3) CurrentPosition.x = -3;

        if(PreviousPosition.x == CurrentPosition.x)
        {
            if (CurrentPosition.x < 0)
                  CurrentPosition.x++;
            else
                CurrentPosition.x--;
        }

        Instantiate(plaform, CurrentPosition, Quaternion.identity);
        moves.Add(x);
       
        PreviousPosition = CurrentPosition;
   
        Destroy(GameObject.Find("platform(Clone)"),8);
         
     }
    

2. **BUCK BASH**

<img width="1233" alt="PUCKBASH" src="https://user-images.githubusercontent.com/68170119/148305820-00bbb340-035e-4659-8673-a67f58d16277.PNG">

3. **ALL THE WAY UP**

<img width="181" alt="ALLTHEWAYUP" src="https://user-images.githubusercontent.com/68170119/148307784-08a41d5d-6228-4c4c-8f65-32097dd5ee10.PNG">


**here some of my code I have wrote in *ALL THE WAY UP* for AI chase the player**.

    void FixedUpdate()
    {
        if (path == null)
        {
            Debug.Log("Enemy");
            return;
        }


        if (currentWaypoint >= path.vectorPath.Count)
        {
            reachEndOfPath = true;
            return;
        }
        else
        {
            reachEndOfPath = false;
        }


        Vector2 direction = ((Vector2)path.vectorPath[currentWaypoint] - rb.position).normalized;
        Vector2 force = direction * speed * Time.deltaTime;


        rb.AddForce(force);
        float distance = Vector2.Distance(rb.position, path.vectorPath[currentWaypoint]);

        if (distance < nextWaypointDistance)
        {
            
            currentWaypoint++;
        }


        if (force.x >= 0.01f)
        {
            transform.localScale = new Vector3(-1.0f, -1.0f, 1.0f);
        }
        else if (force.x <= -0.01f)
        {
            transform.localScale = new Vector3(1.0f, -1.0f, 1.0f);
        }
    }

4. **MAKE ME ANGRY**

**here some of my code I have wrote in *MAKE ME ANGRY GAME* network photon for player choose the chracter role online with other user**.

    void Start()
    {
        spawnPlayer = new SpawnPlayer();
    }
    public void ChoosePlayerOne()
    {
        spawnPlayer.Spawn(mainPlayer1);
    }

    public void ChoosePlayerTwo()
    {
        spawnPlayer.Spawn(mainPlayer2);
    }
