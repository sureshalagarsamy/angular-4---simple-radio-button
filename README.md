# Angular 4 (Radio Button)

The objective is when you click any of the radio button then submit button will be enabled also selected value will be printed in the screen.

Basic useful feature list:

 * Generate list of items
 * onSelect get the selected item
 

##### app.module.ts

```javascript
import { FormsModule } from '@angular/forms';

imports: [
 FormsModule
]
```

##### app.component.html

```html
<span *ngFor="let answer of answerType; let i = index;">
  <input type="radio" name="radioGroup" (click)="showButton(answer)" />{{answer.value}}
</span>
<span class="hide" id="my-submit">
  <button>Submit</button> {{answerObj.model.value}}
</span>
```

##### app.component.html

```css
.hide {
    display: none;
}
```

app.component.ts

```javascript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  answerObj;
  answerType;

  constructor() {
    this.answerType = [{id:1, value:'Yes'},{id:2, value:'No'},{id:3, value:'May be'}];
    this.answerObj = {
      model: this.answerType[0]
    };
  }

  showButton(param) {
    this.answerObj = {
      model: param
    };
    document.getElementById('my-submit').style.display ='block';
  }
}
```

#### Output
![image](https://user-images.githubusercontent.com/6780840/33066569-ad83a8d8-ced1-11e7-84dc-a065770684f1.png)
