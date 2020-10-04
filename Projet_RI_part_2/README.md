# Projet RI partie 2
Le dépôt contient les packages qui contient l’urdf du robot ainsi que les launch file nécessaires à la visualisation des urdf pour le robot avec les jambes additionelles

### part_two_urdf
Contient l'urdf du robot quadruped et le launch file pour visualizer le robot.

### udm_project_moveitconfig
Contient le package udm_project_moveitconfig qui a été généré avec le moveit assistant setup

### udm_project_control
Contient les noeuds, les services et les launch files qui permettent de controler la jambe à travers la cinématique directe ou inverse

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
roslaunch udm_project_control control.launch
```


Ouvrir un troisième terminal dans le catkin workspace et exécuter :

```
source devel/setup.bash
rosservice call /control "mouvement:
 data: 'front'"
```
Les valuers suivantes peuvent etre choisies:'front' , 'right' , 'left' , 'back'. 
