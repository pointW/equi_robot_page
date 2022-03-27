**Abstract:** Recently, equivariant neural network models have been shown to be useful in improving sample efficiency for tasks in computer vision and reinforcement learning. This paper explores this idea in the context of on-robot policy learning where a policy must be learned entirely on a physical robotic system without reference to a model, a simulator, or an offline dataset. We focus on applications of SO(2)-Equivariant SAC to robotic manipulation and explore a number of variations of the algorithm. Ultimately, we demonstrate the ability to learn several non-trivial manipulation tasks completely through on- robot experiences in less than an hour or two of wall clock time.

<style>
.column {
  float: left;
  width: 33.33%;
}
.lc{
  float: left;
  width: 25%;
}
.caption {
    margin: 0;
    vertical-align: baseline;
    text-align: center;
}
img.rounded {
  object-fit: cover;
  border-radius: 50%;
  height: 120px;
  width: 120px;
  margin-left: auto;
  margin-right: auto;
  display: block;
}
.people_column {
  float: left;
  width: 150px;
}
</style>

## Paper
Preprint: [arXiv](https://arxiv.org/pdf/2203.04923.pdf)  

<div style="width:100%; display:flex">
  <div class="people_column">
    <img src="img/dian.jpeg" class="rounded">
    <p class="caption">
      <a href="https://pointw.github.io">Dian Wang</a>
    </p>
  </div>
  <div class="people_column">
    <img src="img/mingxi.jpg" class="rounded">
    <p class="caption">
      <a href="https://saulbatman.github.io">Mingxi Jia</a>
    </p>
  </div>
  <div class="people_column">
    <img src="img/xupeng.jpg" class="rounded">
    <p class="caption">
      <a href="https://zxp-s-works.github.io">Xupeng Zhu</a>
    </p>
  </div>
  <div class="people_column">
    <img src="img/robin.jpeg" class="rounded">
    <p class="caption">
      <a href="http://mathserver.neu.edu/robin/">Robin Walters</a>
    </p>
  </div>
  <div class="people_column">
    <img src="img/rob.jpeg" class="rounded">
    <p class="caption">
      <a href="http://www.ccs.neu.edu/home/rplatt/">Robert Platt</a>
    </p>
  </div>
</div>

Khoury College of Computer Sciences  
Northeastern University

## Idea
We evaluate the on-robot learning using O(2)-Equivariant SAC in four different manipulation tasks. 

<p align="center">
  <img src="img/actor_critic.png" width="600px">
</p>

In O(2)-Equivariant SAC, we hardcode the symmetries of the task in the structure of the actor and the critic to improve the sample efficiency. Specifically, if the input state of the actor (left) is rotated, the output action of the actor will be rotated by the same amount. If the input state and action of the critic (right) are rotated, the output Q-value of the critic will remain the same.

<p align="center">
  <img src="img/env.png" width="100%">
  <p class="caption">The experimental environments. Top: the simulation environments in PyBullet. Bottom: the real-world environments.</p>
</p>

<p align="center">
  <img src="img/table.png" width="70%">
</p>

Our O(2)-Equivariant SAC only requires less than 1 hour to solve Block Picking, Clutter Grasping, and Block Pushing.

<div>
  <div class="lc">
    <img src="img/real_pick.png" style="width:100%">
    <p class="caption">Block Picking</p>
  </div>
  <div class="lc">
    <img src="img/real_grasp.png" style="width:100%">
    <p class="caption">Clutter Grasping</p>
  </div>
  <div class="lc">
    <img src="img/real_push.png" style="width:100%">
    <p class="caption">Block Pushing</p>
  </div>
  <div class="lc">
    <img src="img/real_bowl.png" style="width:100%">
    <p class="caption">Block in Bowl</p>
  </div>
</div>

Compared with the baseline, our method has a much higher sample efficiency in on-robot learning.

## Video

<div style="text-align:center">
	<iframe width="853" height="480" src="https://www.youtube.com/embed/HDYoOXMojkY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</div>

## Citation
{% raw %}
```
@article{wang2022onrobot,
  title={On-Robot Policy Learning with {$\mathrm{O}(2)$}-Equivariant SAC},
  author={Dian Wang and Mingxi Jia and Xupeng Zhu and Robin Walters and Robert Platt},
  journal={arXiv preprint arXiv:2203.04923},
  year={2022}
}
```
{% endraw %}

## Contact
If you have any questions, please feel free to contact [Dian Wang](https://pointw.github.io) at wang[dot]dian[at]northeastern[dot]edu.
