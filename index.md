<html>
	  
<head>
<meta charset="utf-8">
<title>Untitled Document</title>
</head>
 <input type="button" id="calculateBtn" value="Calculator" style="background-color: aqua"/>
                      <div id="callback" ></div>
                    <img id="image" />
<body>
</body>
</html>
 
                    <script src="https://cdn.bootcss.com/jquery/2.1.1/jquery.min.js"></script>
                    <script src="https://calculator.measuresquare.com/scripts/jquery-m2FlooringCalculator.js"></script>

                    <script>
                        $(function () {
                            $('#calculateBtn').m2Calculator({
                                measureSystem: "Metric",
                                showCutSheet: false, // if false, will not include cutsheet section in return image
                                showDiagram: true,  // if false, will close the popup directly 
                                product: {
                                    type: "Carpet",
                                    name: "Carpet 1",
                                    width: "6'0\"",
                                    length: "150'0\"",
                                    horiRepeat: "3'0\"",
                                    vertRepeat: "3'0\"",
                                    horiDrop: "",
                                    vertDrop: ""
                                },
                                cancel: function () {
                                    //when user closes the popup without calculation.
                                },
                                callback: function (data) {
                                    //json format, include user input, usage and base64image
                                    $("#callback").html(JSON.stringify(data));   
                                    console.log(data.input)
                                    $("#usageText").val(data.usage);    
                                    $("#image").attr("src", data.img);  //base64Image
                                }
                            });
                        });
                     </script>
