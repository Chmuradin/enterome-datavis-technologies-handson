<script>
    import { scaleLog } from 'd3-scale';
    import { axisBottom } from 'd3-axis';
    import { select } from 'd3-selection';
    const width = 800;
    const height = 100;
    const margin = { top: 5, right: 5, bottom: 25, left: 5 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;
  
    const values = [2, 4, 6, 7, 9];
    const scale = scaleLog().domain([1,10]).range([0,innerWidth]);
    function axisFunction(element){
    const xAxis = axisBottom(scale);
    xAxis(select(element));
    }
  </script>
  
  <svg viewBox="0 0 {width} {height}">
    <g transform="translate({margin.left},{margin.top})">
    {#each values as v}
      <circle cx={scale(v)} cy={innerHeight/2} r="10"/>
    {/each}
    <text x={innerWidth/2} y={height-margin.top}> x axis </text> 
    </g>
    <g transform="translate({margin.left},{innerHeight})" use:axisFunction>
    </g>
  </svg>
  
  <style>
    circle {
      fill: red;
    }
    text {
      fill: currentColor;
      font-size: 0.67em;
    }
  </style>