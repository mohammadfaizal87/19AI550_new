# Ex.No: 6  Implementation of Jumping  behaviour- Unity
### DATE: 09/09/2025                                                                           
### REGISTER NUMBER : 212223240092
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:
```
1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground
```
###
**Program **
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space) && isGrounded)
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            isGrounded = false;
        }
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Ground"))
        {
            isGrounded = true;
        }
    }
}
```
### Output:

<img width="1919" height="1016" alt="Screenshot 2025-09-09 180311" src="https://github.com/user-attachments/assets/570828d3-d6a3-4131-85c8-e5e9cf27ad80" />



<img width="1919" height="1023" alt="Screenshot 2025-09-09 180330" src="https://github.com/user-attachments/assets/80ab5265-a5a2-47c3-a248-204302ebdf47" />





### Result:
Thus the simple jumping behavior was implemented successfully.
