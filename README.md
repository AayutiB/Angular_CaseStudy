# Angular_CaseStudy
----------ideaboard component ts file---------------------
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-ideaboard',
  templateUrl: './ideaboard.component.html',
  styleUrls: ['./ideaboard.component.css'],
 

})
export class IdeaboardComponent implements OnInit {

  isViewMode:boolean;
  isViewMode1:boolean;
  isViewMode2:boolean;
  section1:string
  section2:string
  section3:string
isDisable:boolean


  constructor() { 
    this.isViewMode=true
    this.isViewMode1=true
    this.isViewMode2=true
this.isDisable=true
    this.section1="what went well"
    this.section2="what can be improved"
    this.section3="Action item"
    console.log("hello")
  }

  ngOnInit() {
    console.log("aayuti")
  }

toggleModeFortitle():void{
this.isViewMode=!this.isViewMode
}
toggleModeFortitle1():void{
  this.isViewMode1=!this.isViewMode1
  }
  toggleModeFortitle2():void{
    this.isViewMode2=!this.isViewMode2
    }

  title = 'Demo2';
  IsWellNoteEdit: boolean = true;

  wellNotes: any = [
    { Id: 0, Text: 'notes here' }
  ];
  improvedNotes: any = [
    { Id: 0, Text: 'Need to be this' }
  ];
  actionnotes: any = [
    { Id: 0, Text: 'Ation items' }
  ];

  addWellSticky() {
    // add note here

    let count = this.wellNotes.length;
    this.wellNotes.push({ Id: count, Text: 'New notes' });
    console.log(this.wellNotes);
  }
  deleteWellSticky(event: any, id: any) {
    // remove item from database here
    // and then remove from Ui

    const index = this.wellNotes.findIndex(c => c.Id == id);
    if (index > -1) {
      this.wellNotes.splice(index, 1);
    }

  }
  saveWellSticky(event: any, id: any) {
    debugger;
    const index = this.wellNotes.findIndex(c => c.Id == id);
    // get value from html


  }

  addImprovedSticky() {
    // add note here

    let count = this.wellNotes.length;
    this.improvedNotes.push({ Id: count, Text: 'New Improve notes' });
    console.log(this.wellNotes);
  }
  deleteImprovedSticky(event: any, id: any) {
    // remove item from database here
    // and then remove from Ui

    const index = this.wellNotes.findIndex(c => c.Id == id);
    if (index > -1) {
      this.improvedNotes.splice(index, 1);
    }

  }
  saveImprovedSticky(event: any, id: any) {
    debugger;
    const index = this.improvedNotes.findIndex(c => c.Id == id);
    // get value from html


  }
  addactionSticky() {
    // add note here

    let count = this.wellNotes.length;
    this.actionnotes.push({ Id: count, Text: 'New notes' });
    console.log(this.wellNotes);
  }
  deleteactionSticky(event: any, id: any) {
    // remove item from database here
    // and then remove from Ui

    const index = this.wellNotes.findIndex(c => c.Id == id);
    if (index > -1) {
      this.actionnotes.splice(index, 1);
    }

  }
  saveactionsticky(event: any, id: any) {
    debugger;
    const index = this.actionnotes.findIndex(c => c.Id == id);
    // get value from html


  }
}
----------------------ts=----------------------
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<!-- * * * * * * * * * * * The content below * * * * * * * * * * * -->
<!-- * * * * * * * * * * is only a placeholder * * * * * * * * * * -->
<!-- * * * * * * * * * * and can be replaced. * * * * * * * * * * * -->
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->
<!-- * * * * * * * * * Delete the template below * * * * * * * * * * -->
<!-- * * * * * * * to get started with your project! * * * * * * * * -->
<!-- * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * -->

<div class="logoContainer">
  <a class="logo" href="#" title="ideaboardz">
    <img src="assets/ideaboardz.png">
  </a>
</div>

<div class="whiteboard">
  <h2 class="ideaBoardTitle" id="ideaBoardTitle" title="Retrospective">daily_retrospective</h2>

  <div class="sections" id="sectionsRow0">

    
        <div class="section oneThird purple ui-droppable " data-color="purple" id="section1">
          <div class="sectionTitleArea">
            <h4 class="sectionTitle">{{this.section1}}
            <td *ngIf="!isViewMode">
              <input [(ngModel)] = "section1">
          </td>
           <td><button disabled="isDisable">save </button></td>>
          <button (click)="toggleModeFortitle()">{{(isViewMode)?"Edit":"Save"}}</button></h4>
            <button title="Add sticky" (click)="addWellSticky()">
              <h3><b>+</b></h3>
            </button>
          </div>
          <div class="row" *ngFor="let note of wellNotes;  let i = index">
            <div class="sticyNote">
             
                <div class="row">
                  <div class="col-sm-6">
                    <button (click)="deleteWellSticky($event,i)" style="padding:5px; margin:5px;">Delete</button>
                    <button (click)="saveWellSticky($event,i)" style="padding:5px; margin:5px;">Save</button>
                  </div>
                </div>
            
              <textarea id="{{i}}" value="{{note.Text}}" class="txtArea1"></textarea>
            </div>
          </div>
        </div>
      
      
        <div class="section oneThird purple ui-droppable " data-color="purple" id="section1">
          <div class="sectionTitleArea">
            <h4 class="sectionTitle">{{this.section2}}
              <td *ngIf="!isViewMode1">
                <input [(ngModel)] = "section2">
            </td>
             
            <button (click)="toggleModeFortitle1()">{{(isViewMode1)?"Edit":"Save"}}</button></h4>
            <button title="Add sticky" (click)="addImprovedSticky()">
              <h3><b>+</b></h3>
            </button>
          </div>
          <div class="row" *ngFor="let note of improvedNotes;  let i = index">
            <div class="sticyNote">
              <div class="hedSticyNote">
                <div class="row">
                  <div class="col-sm-6">
                    <button (click)="deleteImprovedSticky($event,i)" style="padding:5px; margin:5px;">Delete</button>
                    <button (click)="saveImprovedSticky($event,i)" style="padding:5px; margin:5px;">Save</button>
                  </div>
                </div>
              </div>
              <textarea id="{{i}}" value="{{note.Text}}" class="txtArea"></textarea>
            </div>
          </div>
        </div>
        
   
        <div class="section oneThird purple ui-droppable " data-color="purple" id="section1">
          <div class="sectionTitleArea">
        
            <h4 class="sectionTitle">{{this.section3}}
              <td *ngIf="!isViewMode2">
                <input [(ngModel)] = "section3">
            </td>
             
            <button (click)="toggleModeFortitle2()">{{(isViewMode2)?"Edit":"Save"}}</button></h4>
            <button title="Add sticky" (click)="addactionSticky()">
              <h3><b>+</b></h3>
            </button>
          </div>
          <div class="row" *ngFor="let note of actionnotes;  let i = index">
            <div class="sticyNote">
              <div class="hedSticyNote">
                <div class="row">
                  <div class="col-sm-6">
                    <button (click)="deleteactionSticky($event,i)" style="padding:5px; margin:5px;">Delete</button>
                    <button (click)="saveactionsticky($event,i)" style="padding:5px; margin:5px;">Save</button>
                  </div>
                </div>
              </div>
              <textarea id="{{i}}" value="{{note.Text}}" class="txtArea2"></textarea>
            </div>
          </div>
        </div>
        
   
      
    
</div>
----module-ts---------
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from './app.component';
import { EmpComponent } from './emp/emp.component';
import { IdeaboardComponent } from './ideaboard/ideaboard.component';
import { DashboardComponent } from './dashboard/dashboard.component';
import { FormsModule } from '@angular/forms';

@NgModule({
  declarations: [
    AppComponent,
    EmpComponent,
    IdeaboardComponent,
    DashboardComponent
  ],
  imports: [
    BrowserModule,
   FormsModule

  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
--------------csss--------------
.logoContainer{
  float: left;
  width:24%;
  min-width: 250px;
}

.logo{
  margin: 15px 0 15px 15px;
}

.whiteboard{
  text-align: center;
  min-height: 643px;
  background-color: white;
  border: #696969 solid 10px;
  overflow: auto;
  width: 95%;
  border-radius: 5px;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
  border-bottom-left-radius: 5px;
  border-bottom-right-radius: 5px;
  -webkit-border-radius:5px;
}

.whiteboard{
  font-family: 'Delius','Roboto','helvetica','cursive';
}

.sections{
  overflow: auto;
}

.section{
  float: left;
  margin-bottom: 10px;
  min-height: 200px;
}

.oneThird{
  width: 33%;
}

.sectionTitleArea{
  overflow: auto;
  width: 100%;
  padding: 0 0 0.5em 0;
}

.sectionTitle{
  display: inline;
}

h1,h2,h3,h4, .sectionTitle{
  margin: 0.2em 0 ;
  font-family: 'Handlee','Roboto',Helvetica,cursive;
  font-weight: bold;
}

h4{
  font-size: 100%;
}

.addStickyButton{
  color: #83bc2d;
  border: none;
  cursor: pointer;
  overflow: hidden;
  font-size: 1.2em;
  padding: 0.5px;
  background: none;
}

.fa,.fas{
  font-weight: 900;
}

.fa,.far,.fas{
  font-family: "Font Awesome 5 Free";
}

.fa,.fab,.fal,.far,.fas{
  -webkit-font-smoothing:antialiased;
  display: inline;
  font-style: normal;
  font-variant: normal;
  text-rendering: auto;
  line-height: 1;
}

button{
  appearance: auto;
  writing-mode: horizontal-tb;
  -webkit-writing-mode:horizontal-tb !important;
  letter-spacing: normal;
  word-spacing: normal;
  text-transform: none;
  text-indent: 0px;
  text-shadow: none;
  text-align: center;
  align-items: flex-start;
  box-sizing: border-box;
  font: 400 13.3333px Arial; 
}

.fa-plus-circle:before{
  content: "\f055";
}


.sticyNote {
  background-color: rgb(210, 252, 219);   
  border: 2x solid green;
  padding: 4px;
  margin: 4px;
  margin-left: 100px;
  width: 50%;
}

.hedSticyNote {
  padding-right: 65px; 
}
.txtArea{
  border: transparent;
  background-color: rgb(148, 199, 247);
  width:90%;height:90px;
  color: #000;
}
.txtArea1{
  border: transparent;
  background-color: rgb(250, 169, 121);
  width:90%;height:90px;
  color: #000;
}
.txtArea2{
  border: transparent;
  background-color: rgb(202, 253, 154);
  width:90%;height:90px;
  color: #000;
}
 .sectionPad{
  padding: 2px;
  margin: 2px;
 }
