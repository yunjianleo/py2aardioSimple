参考https://github.com/jim4node/py2aardio，改造为插件，这样在工具栏更方便使用。

```javascript
import fonts.fontAwesome;
import win.ui;
import converter;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=569)
winform.add(
btnToPy={cls="button";text="转Python";left=641;top=296;right=752;bottom=329;z=2};
checkbox={cls="checkbox";text="自动复制";left=522;top=301;right=614;bottom=325;checked=1;font=LOGFONT(h=-14);z=4};
editResult={cls="edit";left=13;top=335;right=753;bottom=555;edge=1;multiline=1;vscroll=1;z=3};
editSource={cls="edit";left=11;top=8;right=751;bottom=290;edge=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

vvvv = /****
****/


winform.editSource.text = vvvv;
var convertSingleFile = function(src) {
    if (#src) {
        var cvter = converter(src);
        var result = cvter.go();
        if (result) {
            winform.editResult.text = result;
        } else {
            winform.editResult.print("没有结果");
        }
    }
    if(winform.checkbox.checked == true){
        import win.clip;
        import console;
        //console.log("yyy");
    	//win.clip.write("DFDFD");
    	win.clip.write(winform.editResult.text);
    }
};

winform.btnToPy.oncommand = function(id, event) {
    convertSingleFile(winform.editSource.text);
}


winform.show();
win.loopMessage();
```
