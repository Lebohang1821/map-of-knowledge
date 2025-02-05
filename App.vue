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
          { data: { id: '0', label: '0. Foundations' } },
          { data: { id: '1', label: '1. Basic ROS2' } },
          { data: { id: '2', label: '2. ROS Basics' } },
          { data: { id: '3', label: '3. Intermediate ROS2' } },
          { data: { id: '4', label: '4. Robotics Theory' } },
          { data: { id: '5', label: '5. Navigation ROS2' } },
          { data: { id: '6', label: '6. ROS2 Security' } },
          { data: { id: '7', label: '7. Manipulation' } },
          { data: { id: '8', label: '8. Robot Creation' } },
          { data: { id: '9', label: '9. Artificial Intelligence' } },
          { data: { id: '10', label: '10. ROS Debugging' } },
          { data: { id: '11', label: '11. Course of Product' } },
          { data: { id: '12', label: '12. Web Development for Robots' } },
          { data: { id: '13', label: '13. Simulation' } },
          { data: { id: '14', label: '14. Enterprise' } },
          { data: { id: '15', label: 'C++ Basics for Robotics' } },
          { data: { id: '16', label: 'Python 3 for Robotics' } },
          { data: { id: '17', label: 'Linux for Robotics' } },
          { data: { id: '18', label: 'Create a Link' } },
          { data: { id: '19', label: 'URDF Robot Modelling ROS2' } },
          { data: { id: '20', label: 'ROS2 Basics in 5 Days (C++)' } },
          { data: { id: '21', label: 'ROS2 Basics in 5 Days (Python)' } },
          { data: { id: '22', label: 'ROS2 Basics in 3 Days (Rust)' } },
          { data: { id: '23', label: 'TF in ROS2' } },
          { data: { id: '24', label: 'Intermediate ROS2 (Python)' } },
          { data: { id: '25', label: 'Intermediate ROS2 (C++)' } },
          { data: { id: '26', label: 'ROS2 Control' } },
          { data: { id: '27', label: 'Behavior Trees for ROS2' } },
          { data: { id: '28', label: 'Advanced Modern C++ for Robotics' } },
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
          { data: { source: '3', target: '5' } },
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
        ],
        style: [
          {
            selector: 'node',
            style: {
              'background-color': '#007BFF',
              'label': 'data(label)',
              'text-valign': 'center',
              'text-halign': 'center',
              'color': '#fff',
              'font-size': '14px',
              'font-weight': 'bold',
              'border-width': 3,
              'border-color': '#0056b3',
              'shape': 'roundrectangle',
              'padding': '10px',
              'width': 'label',
              'height': 'label'
            }
          },
          {
            selector: 'node.main',
            style: {
              'background-color': '#FF5733',
              'width': '80px',
              'height': '80px',
              'font-size': '16px',
              'border-color': '#C70039'
            }
          },
          {
            selector: 'node.no-connections',
            style: {
              'background-color': '#B0BEC5',
              'border-color': '#78909C',
              'opacity': 0.6
            }
          },
          {
            selector: 'node.course',
            style: {
              'background-image': 'url(./course-image.png)',
              'background-fit': 'cover',
              'border-width': 0,
              'width': '150px', // Set width to 150px
              'height': '150px', // Set height to 150px
              'font-size': '16px',
              'color': '#000' // Change text color to black for better visibility
            }
          },
          {
            selector: 'node.numbered',
            style: {
              'label': 'data(label)',
              'text-valign': 'center',
              'text-halign': 'center',
              'font-size': '14px',
              'font-weight': 'bold',
              'border-width': 3,
              'shape': 'roundrectangle',
              'padding': '10px',
              'width': 'label',
              'height': 'label'
            }
          },
          {
            selector: 'node.large',
            style: {
              'background-image': 'url(./course-image.png)',
              'background-fit': 'cover',
              'border-width': 0,
              'width': '150px', // Set width to 150px
              'height': '150px', // Set height to 150px
              'font-size': '16px',
              'color': '#000', // Change text color to black for better visibility
              'label': 'data(label)',
              'text-wrap': 'wrap',
              'text-max-width': '140px' // Ensure text fits properly
            }
          },
          {
            selector: 'node:selected',
            style: {
              'background-color': '#FFC107',
              'border-color': '#FFA000',
              'transform': 'scale(1.2)'
            }
          },
          {
            selector: 'node.blurred',
            style: {
              'opacity': 0.3,
              'filter': 'blur(2px)'
            }
          },
          {
            selector: 'edge',
            style: {
              'width': 2,
              'line-color': '#B0BEC5',
              'target-arrow-color': '#B0BEC5',
              'target-arrow-shape': 'triangle',
              'curve-style': 'bezier'
            }
          },
          {
            selector: 'edge.main-connection',
            style: {
              'line-color': '#FF5733',
              'target-arrow-color': '#FF5733',
              'width': 4
            }
          }
        ],
        layout: {
          name: 'cose-bilkent',
          animate: true,
          animationDuration: 1000,
          nodeRepulsion: 10000,
          idealEdgeLength: 150,
          edgeElasticity: 0.3,
          gravity: 0.1,
          nestingFactor: 0.9,
          fit: true,
          padding: 30
        },
        userPanningEnabled: true,
        userZoomingEnabled: true,
        minZoom: 0.5,
        maxZoom: 2
      });

      cy.nodes().forEach(node => {
        if (node.data('label').match(/^\d+\./)) {
          node.addClass('main');
          if (!['12', '9', '14', '4', '11'].includes(node.data('label').split('.')[0])) {
            node.addClass('numbered');
          } else {
            node.addClass('large');
          }
        }
        if (node.degree() === 0) {
          node.addClass('no-connections');
        }
        if (node.data('label').includes('Course')) {
          node.addClass('course');
        }
      });

      cy.edges().forEach(edge => {
        const source = edge.source();
        const target = edge.target();
        if (source.hasClass('main') && target.hasClass('main')) {
          edge.addClass('main-connection');
        }
      });

      cy.on('tap', 'node', function(evt) {
        const node = evt.target;
        cy.elements().removeClass('highlighted blurred');
        node.addClass('highlighted');
        cy.elements().not(node).addClass('blurred');
        cy.animate({
          fit: {
            eles: node,
            padding: 40
          },
          duration: 800
        });
      });

      cy.on('tap', function(evt) {
        if (evt.target === cy) {
          cy.elements().removeClass('highlighted blurred');
          cy.animate({
            fit: {
              eles: cy.elements(),
              padding: 30
            },
            duration: 800
          });
        }
      });

      cy.on('grab', 'node', function(evt) {
        const node = evt.target;
        cy.elements().removeClass('highlighted blurred');
        node.addClass('highlighted');
        cy.elements().not(node).addClass('blurred');
      });

      cy.on('free', 'node', function(evt) {
        const node = evt.target;
        cy.elements().removeClass('highlighted blurred');
        cy.animate({
          fit: {
            eles: cy.elements(),
            padding: 30
          },
          duration: 800
        });
      });
    });
  }
};
</script>

<style>
#cy {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(135deg, #f9f9f9, #e0e0e0);
  transition: background 0.5s ease;
}

#cy:active {
  background: linear-gradient(135deg, #e0e0e0, #f9f9f9);
}
</style>
