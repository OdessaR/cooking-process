cooking-process
===============

Ontology for describing processes in the domain of cooking



Cooking Process Ontology
------------------------
------------------------

1.	Ontology:
	---------

1.1.	First a Recipie class is defined. It is only used to simplify recipe instances, 
	which are defined as individuals of this class.

1.2.	Define and classify ingredient classes and object properties to assign to a recipie
	( Ingredient and hasIngredient ).

1.3.	Define and classify equipment classes and object properties to assign to a recipie
	( Equipment and usesEquipment ).

1.4.	Define the recipie step classes (subclasses of RecipieStep ).

	The system can be used to automatically infer the steps necessary to produce the dish in question.
	The process for creation a dish is composed of these steps, which are represented as defined classes.
	They can be inferred for an recipie individual by the use of ingredients and equipment.

1.5.	Define the ordering object properties ( before ) and ( after ), where before creates the linear ordering
	by being functional, asymmetric and irreflexive. after is defined as being the inverse of before.



2.	Procedure for practical use:
	----------------------------

2.1	Define items used:
	------------------

2.1.1.	Define and classify ingredient individuals
2.1.2.	Define and classify equipment individuals


2.2	Define the recipie:
	-------------------

2.2.1.	Declarate recipie individual, classifying it as a Recipie
2.2.2.	Add ingredients individuals to the recipie individual using the object property hasIngredient
2.2.3.	Add equipment individuals to the recipie individual using the object property usesEquipment


2.3.	Infer the recipie steps:
	------------------------

2.3.1.	If the reasoner is started, the needed recipie steps for producing the dish are inferred.


2.4	Infer the step order:
	---------------------

2.4.1.	For inferring the order of the recipie steps, some preparations are needed.
	Because we did use classes as representations of the recipie steps, no direct ordering can be done.
	Therefore we have to define individuals for the steps and create object properties to connect these steps.

2.4.2	Then for each transition from one step to the next an object property is defined as subproperty of before.
	The preceding step class is used as the domain and the following step class is used as range.
	The order will be linear because of the before superclass. The step individuals are then linked together 
	using these transition object properties.

2.4.3.	If the reasoner is started, the recipie step order and the recipie step classes of the step individuals
	are inferred to create a cooking process description.

