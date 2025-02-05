<template>
    <div id="cy"></div>
  </template>
  
  <script>
  import { onMounted } from 'vue';
  import cytoscape from 'cytoscape';
  import coseBilkent from 'cytoscape-cose-bilkent';
  
  cytoscape.use(coseBilkent);
  
  export default {
    setup() {
      onMounted(() => {
        const cy = cytoscape({
          container: document.getElementById('cy'),
          elements: [
            { data: { id: '0', label: 'Foundations' } },
            { data: { id: '1', label: 'Basic ROS2' } },
            { data: { id: '2', label: 'ROS Basics' } },
            { data: { id: '3', label: 'Intermediate ROS2' } },
            { data: { id: '4', label: 'Robotics Theory' } },
            { data: { id: '5', label: 'Navigation ROS2' } },
            { data: { id: '6', label: 'ROS2 Security' } },
            { data: { id: '7', label: 'Manipulation' } },
            { data: { id: '8', label: 'Robot Creation' } },
            { data: { id: '9', label: 'Artificial Intelligence' } },
            { data: { id: '10', label: 'ROS Debugging' } },
            { data: { id: '11', label: 'Course of Product' } },
            { data: { id: '12', label: 'Web Development for Robots' } },
            { data: { id: '13', label: 'Simulation' } },
            { data: { id: '14', label: 'Enterprise' } },
            { data: { id: '15', label: 'C++ Basics for robotics' } },
            { data: { id: '16', label: 'Python 3 for robotics' } },
            { data: { id: '17', label: 'Linux for robotics' } },
            { data: { id: '18', label: 'create a link' } },
            { data: { id: '19', label: 'URDF robot modelling ROS2' } },
            { data: { id: '20', label: 'ROS2 Basics in 5 days (C++)' } },
            { data: { id: '21', label: 'ROS2 Basics in 5 days (Python)' } },
            { data: { id: '22', label: 'ROS2 Basics in 3 days (Rust)' } },
            { data: { id: '23', label: 'TF in ROS2' } },
            { data: { id: '24', label: 'Intermediate ROS2 (Python)' } },
            { data: { id: '25', label: 'Intermediate ROS2 (C++)' } },
            { data: { id: '26', label: 'ROS2 Control' } },
            { data: { id: '27', label: 'Behavior Trees for ROS2' } },
            { data: { id: '28', label: 'Advanced Modern C++ for robotics' } },
            { data: { id: '29', label: 'ROS1-ROS2 Migration' } },
            { data: { id: '30', label: 'Nav2 Basics' } },
            { data: { id: '31', label: 'Nav Advanced' } },
            { data: { id: '32', label: 'RTAB' } },
            { data: { id: '33', label: 'Gazebo Sim with ROS2' } },
  
            { data: { source: '0', target: '1' } },
            { data: { source: '0', target: '15' } },
            { data: { source: '0', target: '16' } },
            { data: { source: '0', target: '17' } },
            { data: { source: '0', target: '18' } },
            { data: { source: '1', target: '2' } },
            { data: { source: '1', target: '3' } },
            { data: { source: '1', target: '6' } },
            { data: { source: '1', target: '19' } },
            { data: { source: '1', target: '20' } },
            { data: { source: '1', target: '21' } },
            { data: { source: '1', target: '22' } },
            { data: { source: '2', target: '23' } },
            { data: { source: '2', target: '13' } },
            { data: { source: '3', target: '4' } },
            { data: { source: '3', target: '5' } },
            { data: { source: '3', target: '9' } },
            { data: { source: '3', target: '10' } },
            { data: { source: '3', target: '24' } },
            { data: { source: '3', target: '25' } },
            { data: { source: '3', target: '26' } },
            { data: { source: '3', target: '27' } },
            { data: { source: '3', target: '28' } },
            { data: { source: '3', target: '29' } },
            { data: { source: '5', target: '7' } },
            { data: { source: '5', target: '8' } },
            { data: { source: '5', target: '30' } },
            { data: { source: '5', target: '31' } },
            { data: { source: '5', target: '32' } },
            { data: { source: '8', target: '33' } },
            { data: { source: '11', target: '12' } },
            { data: { source: '13', target: '14' } }
          ],
          style: [
            {
              selector: 'node',
              style: {
                'background-color': '#4a90e2',
                'label': 'data(label)',
                'text-valign': 'bottom',
                'text-halign': 'center',
                'color': '#333',
                'font-size': '12px',
                'border-width': 2,
                'border-color': '#2c3e50',
                'shape': 'ellipse',
                'width': '10px',
                'height': '10px'
              }
            },
            {
              selector: 'edge',
              style: {
                'width': 2,
                'line-color': 'rgba(149, 165, 166, 0.1)', // Slightly visible
                'opacity': 0.2, // Set opacity to 1
                'curve-style': 'bezier'
              }
            }
          ],
          layout: {
            name: 'cose-bilkent',
            animate: true,
            animationDuration: 1000,
            nodeRepulsion: 8000,
            idealEdgeLength: 120,
            edgeElasticity: 0.2,
            gravity: 0.2,
            nestingFactor: 0.8
          },
          userPanningEnabled: true,
          userZoomingEnabled: true,
          minZoom: 0.5,
          maxZoom: 2
        });
      });
    }
  };
  </script>
  
  <style>
  #cy {
    width: 100vw;
    height: 100vh;
    background: radial-gradient(circle, #f0f0f0, #dcdcdc);
  }
  </style>
