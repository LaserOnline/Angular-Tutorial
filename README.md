
## 🛠️ Angular

🪄 วิธีการนำ ค่าจาก Typescript มาแสดงผล HTML

app.component.ts
```bash
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'angular_tutorial';
}
```

app.component.html
```bash
<div>
  {{title}}
</div>
```
วิธีนำ value จาก Typescript มาแสดงผลใน value html

ts
```bash
count: number = 0;
```

html
```bash
<input [value]="count">
```

วิธีการ นำค่าจาก Html มายัง Typescript

ts
```bash
callFunc(value: string) {
    const number = Number(value)
    this.value = number
}
```
เครื่องหมาย #ตามด้วยชื่อตัวแปล และส่งข้อมูลไปยัง ฟังชัน

html
```bash
<input #dataInput type="number" value="0" placeholder="data" />
<button (click)="callFunc(dataInput.value)">sum</button>
```

---

♨️ การเรียกใช้ ฟังชัน จาก HTML ไปยัง TypeScript

Event Click

ts
```bash
test() {
  console.log("HelloWorld")
}
```

html
```bash
<button (click)="test()">event</button>
```

---

🚦 How to use @Input

การใช้งาน Input

ts
```bash
import { Input } from '@angular/core';

@Input() count: number = 0;
```

selector
```bash
<app-component [count]="5"></app-component>
```

---

🚥 How to use @Output

EventEmitter

ตัวแปล event จะตัวกำหนด output ในการใช้งาน

ts
```bash
import { EventEmitter, Output }

@Output() event = new EventEmitter

mytest() {
    this.number++;
    console.log(`${this.number}`)
    this.event.emit()
}
```

html 
```bash
<button (click)="mytest()">Output</button>
```

นำ event ที่เป็นตัวแปล output มาผูกกับฟังชันที่ต้องการทำงาน

selector
```bash
<app-component (event)="testClick()"></app-component>
```

