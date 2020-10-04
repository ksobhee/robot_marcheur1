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

## Visualisation de la jambe
### Visualiser la jambe
Pour visualiser, il faut executer le code suivant dans le terminal de votre workspace:

```
source devel/setup.bash
roslaunch part_one_urdf simulate.launch
```
