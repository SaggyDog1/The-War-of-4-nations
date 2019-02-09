# The-War-of-4-nations
This contains all info pertained to The game called "The war of 4 nations"
ALso for info on how it has started to be made here is a link to the only information released to the public on this game 
https://www.youtube.com/watch?v=6Fb-haGId5Y







ALL THE CODE FOR THE ANIMMATIONS ISSUES

Also Here is a all of my code for the CSharp code that I have check it just in case something is wrong with it 





using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class PlayerMovement : MonoBehaviour
{
    Rigidbody2D rbody;
    Animator Anim;
    // Start is called before the first frame update
    void Start()
    {
        rbody = GetComponent<Rigidbody2D> ();
        Anim = GetComponent<Animator> ();
    }

    // Update is called once per frame
    void Update() {
        Vector2 movement_vector2 = new Vector2(Input.GetAxisRaw("Horizontal"), Input.GetAxisRaw("Vertical"));

        if (movement_vector2 != Vector2.zero)
        {
            Anim.SetBool("iswalking", true);
            Anim.SetFloat("input_X", movement_vector2.x);
            Anim.SetFloat("input_Y", movement_vector2.y);
        } else {
            Anim.SetBool ("iswalking", false);
        }
            rbody.MovePosition(rbody.position + movement_vector2 * Time.deltaTime);
        }
    }




it also says this in the console and here is that issue with code
Assets/Tiled2Unity/Scripts/Editor/ImportTiled2Unity.Prefab.cs(93,45): warning CS0618: `UnityEditor.PrefabUtility.CreateEmptyPrefab(string)' is obsolete: `The concept of creating a completely empty Prefab has been discontinued. You can however use SaveAsPrefabAsset with an empty GameObject.'




Code for issue 
                finalPrefab = PrefabUtility.CreateEmptyPrefab(prefabPath);
