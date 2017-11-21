/**
 * Created by 张贺杰 on 2017/8/4.
 */
$.fn.dialog = function (opt) {
    var def = {
        width: "300px",
        height: "300px",
        titles: "",
        content:"",
        anima:"shake"
    };
    var setting = getExt(def,opt);
    var width = setting.width;
    var height = setting.height;
    var titles = setting.titles;
    var content = setting.content;
    var btns = setting.btns;
    var anima = setting.anima;
    var footBtn = $("<div class='footBtn'></div>");
    $("<div class='parents'></div>").css({zIndex:99,width:"100%",height:"100%",position:"absolute",background:"rgba(0,0,0,0.5)",left:0,top:0}).prependTo("body");
    $("<div class='dialog animated'></div>").css({width:width,height:height,paddingLeft:"5px",paddingRight:"5px",position:"absolute",background:"#fff",left:0,right:0,top:0,bottom:0,margin:"auto"}).appendTo(".parents")
    $("<h2 class='title'></h2>").html(titles).appendTo(".dialog");
    $(".title").css({textAlign:"center",lineHeight:"30px",fontWeight:"normal",fontSize:"16px"});
    $("<div class='wrap'></div>").html(content).appendTo(".dialog");
    $(".wrap").css({fontSize:"14px"});
    for(var i = 0; i < btns.length; i ++){
        footBtn.append($("<button>"+btns[i]+"</button>"));
    }
    footBtn.css({position:"absolute",bottom:"10px",left:0,width:"100%",height:"30px","display":"flex","justify-content":"center","align-item":"center"});
    footBtn.find("button").css({borderWidth:0,marginRight:5,padding:"3px 10px"});
    $(".dialog").append(footBtn);
    $(".dialog").addClass(anima);
    setTimeout(function(){
        $(".dialog").removeClass(anima);
    },2000);
    $(footBtn).on("click","button",function(){
        if($(this).html() == "确认"){
            setting.success && setting.success();
            $(".parents").remove();
        }else{
            setting.error && setting.error();
            $(".parents").remove();
        }
    });
    function getExt() {
        for (var i = 1; i < arguments.length; i++) {
            for (var key in arguments[i]) {
                arguments[0][key] = arguments[i][key];
            }
        }
        return arguments[0]
    }
};