# NpyScreen
Fork from https://code.google.com/archive/p/npyscreen/

## Changes
Added custom highlighting for widget and multiline  
Example:  
```python
import npyscreen
class MyForm(npyscreen.FormBaseNew):
    def create(self):
        # BoxTitle used multiline
        obj = self.add(npyscreen.BoxTitle, name="test", custom_highlighting=True, values=["first line", "second line"])
        
        # get colors
        color1 = self.theme_manager.findPair(self, 'DANGER')
        color2 = self.theme_manager.findPair(self, 'IMPORTANT')
        
        # fill line
        obj.entry_widget.highlighting_arr_color_data = [[color1,color1,color2],[color2,color1,color2,color2]]

class App(npyscreen.StandardApp):
    def onStart(self):
        self.addForm("MAIN", MyForm)

obj = App()
obj.run()

```
