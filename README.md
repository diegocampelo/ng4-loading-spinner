# ng4-loading-spinner
Angular 4 custom async loading spinner.

## Note

*This is under maintenance for more configuration. Please use it after the note is removed.*

## Installation

    npm i ng4-loading-spinner --save

## Description 

    Custom loading spinner for Angular 2/4.
    You can override the css for your customized spinner.

## Usage 

1. Import module to your application master module

    `import { Ng4LoadingSpinner } from 'ng4-loading-spinner';`

2. Make an import entry as shown below

    `imports: [ Ng4LoadingSpinner ]`

3. Inject the *SpinnerService* &  to providers 

        @NgModule({
        declarations: [
            AppComponent            
        ],        
        imports: [
            BrowserModule,
            Ng4LoadingSpinner
        ],
        providers: [SpinnerService],
        bootstrap: [AppComponent]
        });

4. Include `<app-spinner> </app-spinner>` to your root level component.

5. Import `SpinnerService` to the component where you want to show the spinner.

    `import { SpinnerService } from './spinner/spinner.service';`

6. Inject dependancy 

    `constructor(`
        `private spinnerService: SpinnerService`
    `) { }`

7. Use `this.spinnerService.show()` method to display the loading spinner.

8. Use `this.spinnerService.hide()` method to hide the loading spinner once the processing is done.

## Example

    this.spinnerService.show();     
    this.http.get(GLOBAL['CONFIG_URL'])
        .subscribe(data => {
            this.spinnerService.hide();
        });
