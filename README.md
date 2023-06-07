# Push-Latch Gripper (PLG) 

This repository contains the source files and an information page on the Push-Latch Gripper (PLG).
Further information is available at the [project page](https://made-iit.github.io/plg/).

## System description

This paper describes the design, fabrication and validation of a ``passive'' monolithic gripper made in AM, whose operation relies on a push-latch mechanism hereafter named Push-Latch Gripper (PLG).
Push-latch mechanisms are commonly employed in different engineering fields (e.g. SD cards insertion/ejection slots, furniture closures, etc.). While several implementations have been documented in the scientific and patent literature, to the best of the author's knowledge, this work presents one of its first implementations in the design of robotic grippers.
The PLG mode of operation is shown in the figure below: 
1. the gripper first approaches the object to be grasped; 
2. when the object and the base of the gripper are in contact, further pushing causes the compliant fingers to close; 
3. once the desired threshold is reached, the gripper fingers lock in place; 
4. the grasped object can now be safely manipulated and moved; 
5. at last, an additional push is needed to release the part. 

![Sequence](/Images/grasping_seq.png)

Since the actuation of the gripper is obtained by moving it (e.g. with a robotic manipulator), the PLG is entirely passive and does not require additional power. This type of solution is not commonly employed in practice, possibly because of its low adaptability. However, industrial pick-and-place applications do not generally require a high degree of flexibility and adaptability, rendering grippers such as the PLG suitable for deployment in these contexts.
Furthermore, the gripper presented in this work also exhibits the interesting features, namely: 

* It is made via AM, thus allowing, fast development iterations and greater design freedom if compared to traditional processes Commercial grippers (e.g. the ones by Festo, Schunk, or BTM) are generally made with metallic materials; in addition, the actuation of a commercial device often requires the integration of on-board complex systems or electronics or pneumatic lines. On the contrary, the PLG is manufactured with polymeric materials and does not require on-board drive systems.
This aspect translates into a lower gripper weight.
* Conventionally designed devices are made of several parts assembled together; instead, the gripper presented in this work is monolithic, thus requiring no assembly operations.
These mechanisms are peculiar because they can be immediately employed once manufactured which translates into time/cost savings.
Since there is no need to precisely mate parts, fabrication processes with looser tolerances (therefore more affordable) can be adopted.
Finally, as no components (e.g. fasteners, bearings, etc.) need to be integrated,  monolithic systems often outperform their traditional counterparts in terms of weight.
* Another interesting feature of the current design is the adoption of compliant joints instead of rotational joints.
In contrast to conventional kinematic pairs, compliant joints display a greater degree of predictability and durability owing to their immunity to wear, despite generally allowing lower ranges of motion.
Compliant joints are also not affected by stick-slip friction thus tend to behave more predictably.
This design approach lends itself well to AM implementations and several examples can be found in the literature.

The PLG physical prototype is shown in the figure below, which also shows the indication and nomenclature of its main elements.

<img src="/Images/whole_gripper.png" alt="Sequence" width="500" title="Whole gripper">

![Sequence](/Images/whole_gripper.png | width=200)

### Linear guides, positive drive cam, spring

The vertical motion of the platform is obtained with a linear guide. In particular, the platform is integrated with an extension that slides relatively to the chassis. The extension is joined with the slider.
The sliding of the guides is possible thanks to the special geometry of the parts.
In particular, the joints must be stable, with a gap as narrow as possible and achievable without supports.
Fig. ~\ref{fig:guide_lineari} shows a representation of the cross-sectional views of the geometries used to construct linear guides.
The gap width adopted in this work is 0.2[mm], namely the smallest value that allowed the free relative motion of the parts.
The unsupported portions of the linear guides have been designed so as to lay at an angle of 45° to the build platform to enable support-free fabrication.
A positive drive cam mechanism, integrated into the slider, controls the fingers position.
The cam follower consists of a metal pin installed on the gripper after the printing phase.
As the pin advances through its path, it reaches four principal positions, represented in the figure below, whose function can be described as follows:

1. in the initial position, the fingers are open, and the pin is in the highest position;
2. as the gripper pushes on the object to be grasped, the moving platform moves upward, thus moving the pin from the initial position to the lowest on the right;
3. as the load is released, the pin moves to the position corresponding to the stable closing of the fingers;
4. a further movement of the platform releases the pin, thus moving it to the low cam position on the left where the fingers are unlocked.

![Cam path](/Images/cam_path.png)

Finally, the elasticity in the mechanism brings the pin back to the initial position where the fingers are completely open.
