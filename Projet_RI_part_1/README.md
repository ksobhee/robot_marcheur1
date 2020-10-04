# Introduction
Le dépôt contient les packages qui contient l’urdf du robot ainsi que les launch file nécessaires à la visualisation des urdf pour le robot avec une jambe.

### part_one_urdf
Contient l'urdf et le base_link du robot ayant une jambe et le launch file qui permet de visualizer la jambe.

### udm_project_moveitconfig
Contient le package udm_project_moveitconfig qui a été généré avec le moveit assistant setup

### udm_project_control
Contient les noeuds, les services et les launch files qui permettent de controler la jambe à travers la cinématique directe ou inverse

## Installation du projet
Les étapes suivant doivent être exécutés dans le Catkin workspace:

```
cd catkin_ws/src
git clone https://github.com/ksobhee/robot_marcheur1.git
catkin build
cd ..
source devel/setup.bash
```

## Execution du projet
### Pour visualiser la jambe

```
source devel/setup.bash
roslaunch part_one_urdf simulate.launch
```

### Pour Controler la jambe à l'aide de la cinématique directe
Dans le terminal qui est déjà ouvert sur le catkin workspace, exécuter les commandes suivantes:

```
source devel/setup.bash
roslaunch udm_project_moveitconfig demo.launch
```

Ouvrir un autre terminal sur  le catkin workspace et exécuter:

```
source devel/setup.bash
roslaunch udm_project_control direct.launch
```

Ouvrir un troisième terminal dans le catkin workspace et exécuter :

```
source devel/setup.bash
rosservice call /direct_kin_service_legmr "joint1:
 data: -0.4
joint2:
 data: -0.4
joint3:
 data: 0.2
joint4:
 data: -0.3"
```

Les valeurs peuvent être modifiées pour comprendre l'impacte des modifications

### Pour controler la jambe à l'aide de la cinématique inverse

Dans le premier terminal du catkin workspace, exécuter:

```
source devel/setup.bash
roslaunch udm_project_moveitconfig demo.launch
```

Ouvrir un deuxième terminal dans le catkin workspace et exécuter:

```
source devel/setup.bash
roslaunch udm_project_control indirect.launch
```

Dans un troisième terminal du catkin workspace, exécuter:

```
source devel/setup.bash
rosservice call /indirect_kin_service_legmr "pose:
 orientation:
  w: 1
 position:
  x: 0.4
 position:
  y: 0.4
 position:
  z: -0.2"
```

Les valeurs peuvent être modifiées pour comprendre l'impacte des modifications
