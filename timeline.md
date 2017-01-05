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
  var date = new Date()
  var m = date.getMonth()
  var d = date.getDate()
  var y = date.getFullYear()

  // Create a DataSet (allows two way data-binding)
  var items = new vis.DataSet([
    {id: 1, content: 'Finish novel',          start: '2017-01-01', end: '2017-01-01'},
    {id: 2, content: 'Proofread',             start: '2017-01-02', end: '2017-01-02'},
    {id: 3, content: 'Press release',         start: '2017-01-03', end: '2017-01-03' },
    {id: 4, content: 'Tweet 1-3 times/week',  start: '2017-01-01', end: '2017-01-30' }
    /*
    {id: 1, content: 'Finish novel', start: y + '-' + m + '-' + d },
    {id: 2, content: 'Proofread', start: y + '-' + m + '-' + (d + 1) },
    {id: 3, content: 'Press release', start: y + '-' + m + '-' + (d + 2) }

    {id: 2, content: 'item 2', start: y + '-' + m + '-' + d },
    {id: 3, content: 'item 3', start: '2014-04-18'},
    {id: 4, content: 'item 4', start: '2014-04-16', end: '2014-04-19'},
    {id: 5, content: 'item 5', start: '2014-04-25'},
    {id: 6, content: 'item 6', start: '2014-04-27', type: 'point'}
    */
  ]);

  // Configuration for the Timeline
  var options = {};

  // Create a Timeline
  var timeline = new vis.Timeline(container, items, options);
</script>
