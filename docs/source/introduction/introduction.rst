=================
Introduction
=================

.. role:: raw-html(raw)
    :format: html

.. |CTU_MRS| raw:: html

    <a href="https://ctu-mrs.github.io/" target="_blank">CTU MRS open source platform</a>

To exploit multicore processor capabilities, we have developed a ROS-based system architecture whereby we have split all separate tasks (e.g., pre-stabilizing control, trajectory-based ERG, reference selector, RRT-Connect planner, visualizations) over different ROS nodes such that they can all run in parallel.

Note that exploiting these multicore processor capabilities is extremely important for control algorithms that run at high rates and require data from multiple other running processes while the robot needs to receive control commands at 1kHz and stops when there are too many data losses. We did not do this from the start, but the more high-computational demanding processes we added to our framework (e.g., planning, collision checking), the more communication delays we encountered whereby the robot stopped. The only solution to this problem was to run all the different tasks in parallel, which also made our proposed architecture modular. 

We have grouped these ROS nodes in different ROS packages. All these ROS packages can be found in https://github.com/panda-brubotics which will be made public in the (near) future. 

To develop this ROS-based system architecture, we have taken inspiration from the |CTU_MRS|, i.e., the Multi-robot Systems Group robotics lab at the Czech Technical University in Prague who mostly works with multi-rotor drones, and for them specifically, developed a control, estimation, and simulation platform enabling real-world and replicable simulations and experiments.
