
<link rel="stylesheet" type="text/css" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css/">


# Timeline -- What to do in what order

The order you do things is important. For example:

* Amazon has a program called [KDP Select](https://kdp.amazon.com/select) you can use to 
raise your profile and launch your book effectively. However, they require that you
initially publish your book only on Kindle (you can publish on other sites 30 days later). 
If you choose to use KDP Select it should be your first stop on the publishing timeline.
* You are relying on communities of both readers and writers to help spread the word. 
That means you should at least spend some time learning how these communities work.
Otherwise, you'll hurt yourself by coming off as clueless and purely self-promoting.

## Vis.js timeline test
<link href="https://cdnjs.cloudflare.com/ajax/libs/vis/4.17.0/vis-timeline-graph2d.min.css" rel="stylesheet" type="text/css" />

<script
  src="https://cdnjs.cloudflare.com/ajax/libs/vis/4.17.0/vis.js"
  crossorigin="anonymous"></script>

<div id="visualization"></div>

<script type="text/javascript">
  // DOM element where the Timeline will be attached
  var container = document.getElementById('visualization');

  // Create a DataSet (allows two way data-binding)
  var items = new vis.DataSet([
    {id: 1, content: 'item 1', start: '2014-04-20'},
    {id: 2, content: 'item 2', start: '2014-04-14'},
    {id: 3, content: 'item 3', start: '2014-04-18'},
    {id: 4, content: 'item 4', start: '2014-04-16', end: '2014-04-19'},
    {id: 5, content: 'item 5', start: '2014-04-25'},
    {id: 6, content: 'item 6', start: '2014-04-27', type: 'point'}
  ]);

  // Configuration for the Timeline
  var options = {};

  // Create a Timeline
  var timeline = new vis.Timeline(container, items, options);
</script>
## I wish my timeline were here!

<div class="chart-container">
  <div id="timeline"></div>
</div>

<script
  src="https://code.jquery.com/jquery-3.1.1.slim.min.js"
  integrity="sha256-/SIrNqv8h6QGKDuNoLGA4iret+kyesCkHGzVUUV0shc="
  crossorigin="anonymous"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/labella/1.1.2/labella.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/4.4.0/d3.min.js"></script>
<script type="text/javascript">

// ---------------------------------------------------
// Create dummy data
// ---------------------------------------------------

var data = [
  {date: new Date(1977, 4,25), episode: 4, name: 'A New Hope'},
  {date: new Date(1980, 4,17), episode: 5, name: 'The Empire Strikes Back'},
  {date: new Date(1984, 4,25), episode: 6, name: 'Return of the Jedi'},
  {date: new Date(1999, 4,19), episode: 1, name: 'The Phantom Menace'},
  {date: new Date(2002, 4,16), episode: 2, name: 'Attack of the Clones'},
  {date: new Date(2005, 4,19), episode: 3, name: 'Revenge of the Sith'},
  {date: new Date(2015,11,18), episode: 7, name: 'The Force Awakens'},
];

var options =   {
  margin: {left: 20, right: 20, top: 20, bottom: 20},
  initialWidth: 300,
  initialHeight: 220
};

var innerWidth =  options.initialWidth - options.margin.left - options.margin.right;
var innerHeight = options.initialHeight - options.margin.top - options.margin.bottom;
//var colorScale = d3.scale.category10();

var vis = d3.select('#timeline')
  .append('svg')
    .attr('width',  options.initialWidth)
    .attr('height', options.initialHeight)
  .append('g')
    .attr('transform', 'translate('+(options.margin.left)+','+(options.margin.top)+')');

function labelText(d){
  return d.date.getFullYear() + ' - ' + d.name;
}

// compute labels dimension
var dummyText = vis.append('text');

var timeScale = d3.time.scale()
  .domain(d3.extent(data, function(d){return d.date;}))
  .range([0, innerHeight])
  .nice();

var nodes = data.map(function(movie){
  var bbox = dummyText.text(labelText(movie))[0][0].getBBox();
  movie.h = bbox.height;
  movie.w = bbox.width;
  return new labella.Node(timeScale(movie.date), movie.h + 4, movie);
});

dummyText.remove();

// ---------------------------------------------------
// Draw dots on the timeline
// ---------------------------------------------------

vis.append('line')
  .classed('timeline', true)
  .attr('y2', innerHeight);

var linkLayer = vis.append('g');
var labelLayer = vis.append('g');
var dotLayer = vis.append('g');

dotLayer.selectAll('circle.dot')
  .data(nodes)
.enter().append('circle')
  .classed('dot', true)
  .attr('r', 3)
  .attr('cy', function(d){return d.getRoot().idealPos;});

function color(d,i){
  return '#888';
}

//---------------------------------------------------
// Labella has utility to help rendering
//---------------------------------------------------

var renderer = new labella.Renderer({
  layerGap: 60,
  nodeHeight: nodes[0].width,
  direction: 'right'
});

function draw(nodes){
  // Add x,y,dx,dy to node
  renderer.layout(nodes);

  // Draw label rectangles
  var sEnter = labelLayer.selectAll('rect.flag')
    .data(nodes)
  .enter().append('g')
    .attr('transform', function(d){return 'translate('+(d.x)+','+(d.y-d.dy/2)+')';});

  sEnter
    .append('rect')
    .classed('flag', true)
    .attr('width', function(d){ return d.data.w + 9; })
    .attr('height', function(d){ return d.dy; })
    .attr('rx', 2)
    .attr('ry', 2)
    .style('fill', color);

  sEnter.append('text')
    .attr('x', 4)
    .attr('y', 15)
    .style('fill', '#fff')
    .text(function(d){return labelText(d.data);});

  // Draw path from point on the timeline to the label rectangle
  linkLayer.selectAll('path.link')
    .data(nodes)
  .enter().append('path')
    .classed('link', true)
    .attr('d', function(d){return renderer.generatePath(d);})
    .style('stroke', color)
    .style('stroke-width',2)
    .style('opacity', 0.6)
    .style('fill', 'none');
}

//---------------------------------------------------
// Use labella.Force to place the labels
//---------------------------------------------------

var force = new labella.Force({
  minPos: -10
})
  .nodes(nodes)
  .compute();

draw(force.nodes());

</script>
