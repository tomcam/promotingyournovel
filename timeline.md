# Timeline -- What to do in what order

The order you do things is important. For example:

* Amazon has a program called [KDP Select](https://kdp.amazon.com/select) you can use to 
raise your profile and launch your book effectively. However, they require that you
initially publish your book only on Kindle (you can publish on other sites 30 days later). 
If you choose to use KDP Select it should be your first stop on the publishing timeline.
* You are relying on communities of both readers and writers to help spread the word. 
That means you should at least spend some time learning how these communities work.
Otherwise, you'll hurt yourself by coming off as clueless and purely self-promoting.

## Click to learn more about any step
<link href="https://cdnjs.cloudflare.com/ajax/libs/vis/4.17.0/vis-timeline-graph2d.min.css" rel="stylesheet" type="text/css" />

<script
  src="https://cdnjs.cloudflare.com/ajax/libs/vis/4.17.0/vis.js"
  crossorigin="anonymous"></script>

<div id="visualization"></div>

<script type="text/javascript">

	// Thanks, Anthony Jones (http://stackoverflow.com/users/17516/anthonywjones)
	// for addDays() http://stackoverflow.com/questions/563406/add-days-to-javascript-date
	Date.prototype.addDays = function(days) {
		var dat = new Date(this.valueOf());
		dat.setDate(dat.getDate() + days);
		return dat;
	}
	
  // DOM element where the Timeline will be attached
  var container = document.getElementById('visualization');
  var today = new Date()
  var m = today.getMonth()
  var d = today.getDate()
  var y = today.getFullYear()

  // Create a DataSet (allows two way data-binding)
  var items = new vis.DataSet([
    {id: 1, content: '<a href="/checklist/create-twitter-account/">Create Twitter Account</a>',  start: today.addDays(1) },
    {id: 2, content: '<a href="about">Proofread</a>',             start: today.addDays(2)},
    {id: 3, content: 'Press release',         start: today.addDays(3)},
    {id: 4, content: 'Tweet 1-3 times/week',  start: today.addDays(1), end: today.addDays(60)}
    /*
    {id: 1, content: '<a href="/checklist/create-twitter-account/">Create Twitter Account</a>',  start: today.addDays(2) },
    {id: 2, content: '<a href="about">Proofread</a>',             start: '2017-01-02'},
    {id: 3, content: 'Press release',         start: '2017-01-03'},
    {id: 4, content: 'Tweet 1-3 times/week',  start: '2017-01-04', end: '2017-01-30'}

	{id: 5, content: 'item 5', start: '2014-04-25'},
    {id: 6, content: 'item 6', start: '2014-04-27', type: 'point'}
    */
  ]);

  // Configuration for the Timeline
  var options = {};

  // Create a Timeline
  var timeline = new vis.Timeline(container, items, options);
</script>
