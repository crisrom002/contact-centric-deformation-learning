# Contact-Centric Deformation Learning

![Teaser](assets/images/teaser.png "Teaser image")

[[Project website](http://mslab.es/projects/ContactCentricLearning/)] [[Video](https://www.youtube.com/watch?v=f2WBji-R2uQ)] [[Data](https://urjc-my.sharepoint.com/:f:/g/personal/cristian_romero_urjc_es/Et30gmexC45Mn-OCDo_DdHwB3Y9Skd-S5LDdgjrl_oMNrg?e=9tDYNZ)]

## Abstract

> We propose a novel method to machine-learn highly detailed, nonlinear contact deformations for real-time dynamic simulation. We depart from previous deformation-learning strategies, and model contact deformations in a contact-centric manner. This strategy shows excellent generalization with respect to the object's configuration space, and it allows for simple and accurate learning. We complement the contact-centric learning strategy with two additional key ingredients: learning a continuous vector field of contact deformations, instead of a discrete approximation; and sparsifying the mapping between the contact configuration and contact deformations. These two ingredients further contribute to the accuracy, efficiency, and generalization of the method. We integrate our learning-based contact deformation model with subspace dynamics, showing real-time dynamic simulations with fine contact deformation detail.

**Project structure**:
```
contact-centric-deformation-learning
│
└───assets 
|    └─ images
|    └─ textures
|
└───data 
     └─ meshes.h5              # Mesh data (external download)
     └─ dataset.h5             # Learning data (external download)
 
```

**Requirements**: ```python3```, ```h5py``` ```numpy```

# Meshes

| Key          | Key      | Description                        | Dimension                           |
|--------------|----------|------------------------------------|-------------------------------------|
|  *jelly*     | *W*      | Linear basis (BGBC)                | [num_jelly_nodes, num_handle_rows]  |
|              | *q_ref*  | Reference transformations          | [num_handle_rows, dim]              |
|              | *tris*   | Triangle indices                   | [num_jelly_tris, dim+1]             |
|              | *uv_coords* | uv texture coordinates          | [num_jelly_nodes, dim]              |
|              | *uv_indices*  | uv indices per triangle       | [num_jelly_tris, dim+1]             |
|  *star*      | *W*      | Linear basis (rigid)               | [num_star_nodes, dim+1]             |
|              | *z_ref*  | Reference transformation           | [dim+1, dim]                        |
|              | *tris*   | Triangle indices                   | [num_star_tris, dim+1]              |

# Dataset

| Key    | Description                   | Dimension                            |
|--------|-------------------------------|--------------------------------------|
| *q*    | Handle transformations        | [num_samples, num_handle_rows, dim]  |
| *z*    | Collider transformation       | [num_samples, dim+1, dim]            |
| *x*    | Simulated node positions      | [num_samples, num_jelly_nodes, dim]  |

```
@article {romero2021subspacelearning,
    author  = {Romero, Cristian and Casas, Dan and Pérez, Jesús and Otaduy, Miguel A.},
    title   = {{Learning Contact Corrections for Handle-Based Subspace Dynamics}},
    number  = "4",
    volume  = "40",
    journal = {ACM Transactions on Graphics (Proc. of ACM SIGGRAPH)},
    year    = {2021}
}
```
