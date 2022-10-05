# Computer-Aided-Engineer-Works-Abaqus-CAE-

### My Project topic is:
# 10.5 Example: blast loading on a stiffened plate

I created a three-dimensional  deformable part featuring an extruded shell base to represent the plate. I used about 5.0 piece size and named the piece Plate.

I defined the stiffener geometry, added three vertical lines extending up from the plate. 

I constrained the three vertical lines so they are of equal length, and dimension one of them so that it is 0.1 m long.

I splited the plate at the points where it intersects the stiffeners.

I dimensioned the horizontal distance between the plate endpoints, and set the value to 2.0 m.

I applied equal length constraints to the four horizontal segments of the line.

I extruded the sketch to a depth of 2.0 m to create the plate.

I defined the material and section properties for the plate and the stiffeners.

*I created a material named "Steel" with a "mass density" of 7800 kg/m3, a "Young's modulus" of 210.0E9 Pa, and a "Poisson's" ratio of 0.3.

*The initial yield stress is 300 MPa, and the yield stress increases to 400 MPa at a plastic strain of 35%.

* The data are regularized by Abaqus/Explicit by expanding the data to 15 equally spaced points with increments of 0.025.

*I was set the regularization tolerance back to the default value (0.03) and remove the additional pair of data points.

*I created two homogeneous shell section properties, each referring to the steel material definition but specifying different shell thicknesses.

*I named the first shell section property PlateSection, select Steel as the material, and specify 0.025 m as the value for the Shell thickness.

*I named the second shell section property StiffSection, select Steel as the material, and specify 0.0125 m as the value for the Shell thickness.

*I assigned the StiffSection definition to the stiffeners (I used [Shift] + Click to select multiple regions in the viewport).

*I was query the shell normals (ToolsQuery) and note the color of the side of the plate facing the stiffeners (brown is the positive side; purple is the negative side).

*I was  assign the PlateSection definition to the regions of the plate.

*I was in the Edit Section Assignment dialog box, set the shell offset to Top surfaced if the brown (positive) side of the plate faces the stiffeners and Bottom surfaced if the purple (negative) side faces the stiffeners.

*I was to verify the offset, selected ViewPart Display Options.

* I was in the Part Display Options dialog box that appears, toggled on Render shell thickness. I modified the offset to removed any overlap.
* 
*I created one set named Edge for the plate edges and one set named Center at the center of the intersection of the plate and the middle stiffener.I was To create the set Center, you need to first partition the edge of the original part in half using the Partition Edge: I Entered Parameter  tool.

*I created a single dynamic, explicit step. I named the step Blast.I applied blast loading. I entered a value of 50E-3 s for the time period of the step.

*I  tried to limit the number of frames written during the analysis to keep the size of the output database file reasonable.

*In this analysis saving information every 2 ms should provide sufficient detail to study the response of the structure. 

*I created a history output request named Center-U2 for the step Blast.

*I selected Center as the output domain, and select U2 as the translation output variable. 

*I entered 500 as the number of intervals at which the output will be saved during the analysis.

*In the step Blast, I created a Symmetry/Antisymmetry/Encastre mechanical boundary condition named Fix edges. 

*I applied the boundary condition to the edges of the plate using the geometry set Edge, and specify ENCASTRE (U1 = U2 = U3 = UR1 = UR2 = UR3 = 0) to fully constrain the set.

*In the Model Tree, I double-clicked the Loads container. 

*In the Created Load dialog box that appears, I named the load Pressure load and selected Blast as the step in which it will be applied. 

*I selected Mechanical as the load category and Pressure as the load type.

*I selected all the surfaces associated with the plate. When I the appropriate surfaces are selected, I clicked Done.

*I created a job named BlastLoad.  I blasted load on a flat plate with stiffeners: S4R elements (20x20 mesh) Normal stiffeners (20x2).

*I saved your model in a model database file, and submit the job for analysis. 


![image](https://user-images.githubusercontent.com/61595808/194041560-e4b635c8-1804-45a2-a795-e617165efb8f.png)


![image](https://user-images.githubusercontent.com/61595808/194041583-94fc6670-b51e-43d3-93d9-86098f56849a.png)

![image](https://user-images.githubusercontent.com/61595808/194041599-5b06d973-62ce-418d-9252-ba38c9eb43fd.png)

![image](https://user-images.githubusercontent.com/61595808/194041613-d3072816-5358-48c7-99f3-c1032b0e5d5d.png)

![image](https://user-images.githubusercontent.com/61595808/194041632-35eecec3-3ad4-4ad8-a074-66b5c427d288.png)

![image](https://user-images.githubusercontent.com/61595808/194041646-559cb8f9-1ad9-4121-9587-f7109c4abc25.png)

![image](https://user-images.githubusercontent.com/61595808/194041672-8e677c7e-080c-4d63-aba0-6b856c76eab0.png)

Firstly, click on “Create Part”. I choose what I have to choose.

![image](https://user-images.githubusercontent.com/61595808/194041708-63994ef1-fe80-4756-b20f-f2723016de20.png)

Some of my transactions:

I click on" Create Line " and show the direction I will draw.

![image](https://user-images.githubusercontent.com/61595808/194041745-e8731699-d561-494c-bbe6-805eb1f8255c.png)

![image](https://user-images.githubusercontent.com/61595808/194041773-10315765-91aa-4758-93c3-b40bf93ca103.png)

We click "Add Constraint" and choose "equal Length" from it

![image](https://user-images.githubusercontent.com/61595808/194041809-2161151d-ccc6-4196-979d-d4adfbc4cc74.png)

![image](https://user-images.githubusercontent.com/61595808/194041823-29558d8a-2caa-44ee-a5af-ac6dce2fa96e.png)

![image](https://user-images.githubusercontent.com/61595808/194041839-3856bec4-a725-4ec8-b50a-a7a2d98198a2.png)

![image](https://user-images.githubusercontent.com/61595808/194041860-66a272a8-969e-48aa-9749-44b3fd591e25.png)

![image](https://user-images.githubusercontent.com/61595808/194041878-515c3e06-4ecc-44e4-9858-ea7fa7d9ad51.png)


![image](https://user-images.githubusercontent.com/61595808/194041897-ca246ffe-37fd-490d-9ea6-69d656e08602.png)


![image](https://user-images.githubusercontent.com/61595808/194041912-fb4f0762-f692-4912-88a8-f015fcee57aa.png)


![image](https://user-images.githubusercontent.com/61595808/194041934-11f8e98e-b0c0-4e11-9154-ef968bdfc61f.png)

![image](https://user-images.githubusercontent.com/61595808/194041951-94927107-ac98-4721-bf01-1339a9450f47.png)

![image](https://user-images.githubusercontent.com/61595808/194041971-a599f458-afa1-44ec-aba4-96a246ee9653.png)


![image](https://user-images.githubusercontent.com/61595808/194041982-93422612-7bb7-444f-be86-b4908456d1fc.png)


![image](https://user-images.githubusercontent.com/61595808/194041998-25686945-6e47-4ce4-9fd1-5b81c3d268e7.png)


![image](https://user-images.githubusercontent.com/61595808/194042024-84a0fc2a-877b-4121-acc3-906b1c0d48de.png)


![image](https://user-images.githubusercontent.com/61595808/194042040-9f85e13e-1719-425b-a612-7b8aff62f751.png)


![image](https://user-images.githubusercontent.com/61595808/194042063-329a8175-0955-4510-92e7-624a085d4cb4.png)

![image](https://user-images.githubusercontent.com/61595808/194042081-8d42393c-0392-4f89-b674-383a4351acf5.png)

![image](https://user-images.githubusercontent.com/61595808/194042100-d49c35ca-19f4-4d20-949a-e7c382861699.png)

![image](https://user-images.githubusercontent.com/61595808/194042115-ae76fd60-a613-4734-8901-bba3d09ee49f.png)

![image](https://user-images.githubusercontent.com/61595808/194042131-95348211-83f8-4a41-85b3-52badadb2af6.png)

![image](https://user-images.githubusercontent.com/61595808/194042152-768738ef-0c49-47a8-b45c-bf65b805d9a1.png)

![image](https://user-images.githubusercontent.com/61595808/194042175-a4845d2c-3f89-4241-a353-de68eaa9aa33.png)

![image](https://user-images.githubusercontent.com/61595808/194042193-40727ab7-94ee-447b-a720-e0cbc1d37c58.png)

![image](https://user-images.githubusercontent.com/61595808/194042210-84ba47dd-6237-4f71-aaae-c5f54a302120.png)

![image](https://user-images.githubusercontent.com/61595808/194042220-7b302eb5-385f-4b9d-b6a5-d32b2482e4d3.png)

![image](https://user-images.githubusercontent.com/61595808/194042241-95d7d83b-c4fa-47d1-abdb-9ec12aa39b64.png)

![image](https://user-images.githubusercontent.com/61595808/194042264-3107b8fc-f006-4306-815b-c93f432adacf.png)

