<div id="sortableTrash" class="sortable-code"></div> 
<div id="sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="feedbackLink" value="Get Feedback" type="button" /> 
    <input id="newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "def linear_search(items, items_to_find):\n" +
    "  index = 0\n" +
    "  found = False\n" +
    "  #check every item until found or until there are no more items to check\n" +
    "  while not found and index &lt; len(items):\n" +
    "    if items[index] == items_to_find:\n" +
    "      found = True\n" +
    "    else:\n" +
    "      index = index + 1\n" +
    "  if found:\n" +
    "    print(&quot;Item found at possition&quot;,index)\n" +
    "  else:\n" +
    "    print(&quot;Item not found&quot;)\n" +
    "#main program\n" +
    "items = [&quot;Florida&quot;, &quot;Georgia&quot;, &quot;Deleware&quot;, &quot;Alabama&quot;, &quot;California&quot;]\n" +
    "items_to_find = input(&quot;Enter the state to find: &quot;)\n" +
    "linear_search(items, items_to_find)   ";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
