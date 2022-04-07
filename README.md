# NBKOJ
$(document).ready(function(){
  document.title = document.title.replace("DMOJ", "Dank Memes Online Judge");
  $("#page-container").css({background: "#FFFDF0"});
  $("body").css({background: "#FFF8E8"});
  $("#problem-table tr:even").css("background", "#FFF8E8");
  $(".contest-list tr:even").css("background", "#FFF8E8");
  $("pre").css({background: "#FFF8E8"});
  $(".comment-display").css({background: "#FFFFFF"});
  $('head').append('<style>#submissions-table tr:hover{background:#FFF8E8;}</style>');
  const f = s=>`<span style="background-color:rgba(247,196,0,0.5)">${s}</span>`;
  $('code').html((i,obj) => obj
    .replaceAll(/\w  +\S/g,s=>s[0]+f(s.slice(1,-1))+s.slice(-1))
    .replaceAll(/ +\n/g,s=>f(s.slice(0,-1))+'\n')
    .replaceAll(/ +$/g,s=>f(s)+'\n'));
  $('h2').click(() => {
    $('td.user-name').map((i,td) => {if (td.children && td.children.length>1 && td.children[1].innerText==='Participation ended.') td.parentElement.remove();});
    $('td.user-name').map((i,td) => {if (td.children && td.children.length>1 && td.children[1].innerText!=='Participation ended.') {const a=td.children[0].children[0];a.innerText=`${a.innerText} (${td.children[1].children[0].title})`;}});
  });
});
