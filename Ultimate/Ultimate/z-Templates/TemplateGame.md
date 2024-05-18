<%*
let tournament = await tp.system.prompt("Tournament?");
let opponents = await tp.system.prompt("Opponents?");
let type = await tp.system.suggester(["Pool", "Power Pool", "Pre-Quarter", "Quarter", "Semi", "Final"], ["Pool", "Power Pool", "Pre-Quarter", "Quarter", "Semi", "Final"]);
let ourScore = await tp.system.prompt("Our Score?");
let theirScore = await tp.system.prompt("Their Score?");
-%>
---
noteType: game
tournament: <%* tR += tournament; %>
opponents: <%* tR += opponents; %>
gameType: <%* tR += type; %>
ourScore: <%* tR += ourScore; %>
theirScore: <%* tR += theirScore; %>
---
<%* await tp.file.move("/Tournaments/"+ tournament +"/Games/" + opponents + "/GameOverview") %>



