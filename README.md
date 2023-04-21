# ignition-gazebo

### Terminology 📚

* **World :** The complete description of the simulation ( can contain static or dynamic objects, scenes, plugins, GUI etc). It is contained in a **SDF** (Simulation Description Format) file.

* **Entity :** An 'object' in the world, defined by a Numeric ID provided at run time, it contains components inside it.

* **Component :** It is something that gives a charateristic or fucntionality to the Component.(Pose, name, material etc)

* **System :** It is basically a logic that is applied/operates on all entities having some predifined components. These are runtime loadable plugins.

* **ECM - Entity Component Manager :** A class providing [API](https://ignitionrobotics.org/api/gazebo/1.0/classignition_1_1gazebo_1_1EntityComponentManager.html) for dealing with functionalities like creating, removing, updatinig and querying entities.

* **Level :** Part of the world defined by a box volume and static entities inside it. Levels may overlap each other and an entity may be present in one or more levels.

* **Buffer Zone :** Inflation of the level's volume outside its boundaries. used to detect whether a performer (entity) belong to a particular level or not.

* **Performer :** A moving entity that change levels during simulation (robots, actors or dynamic models). A performer is meaningful only if there are levels.

* **Global Entity :** An entity that is present on all level. eg: light source -> sun, ground plane, height maps etc.

* **Default Level :** Level which handles all entities that are not within any other levels.

* **Network Manager :** A manager of information flow across distributed simulation processes. For a distributed simulation there are **Pirmary manager** and multiple **Secondary Managers**. The primary ensures that all the secondary managers are in sync. If the simulation is not distributed then there is no need for network managers.

* **Event Manager :** Manages events that can be sent across systems and servers.

* **Simulation Runner :** Runner that runs simulation ( world or some levels) no support for running multiple worlds parallely, contains a single ECM, event maanger, network manager(if simulation is distributed), loads up a set of systems.
 
* **Server :** The entry point for ignition gazebo. It loads the **SDF** file and instantiates simulation runner per world. 
