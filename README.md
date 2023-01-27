# Testing AngularJS Components
### beforeEach Setup
```
var $componentController;

beforeEach(module('MyApp'));

beforeEach(inject(function(_$componentController_){
    $componentController = _$componentController_;
}));
```
### Test Method
```
it('should update value', function(){
    var bindings = {
        prop1: {val: 'some val'}
    };

    var ctrl = $componentController('myComp', {}, bindings);

    var updatedVal1 = ctrl.val;

    expect(updatedVal).toEqual('some val');
});
```
***
#### _Summary_
Use the following steps to test a component:
* In beforeEach:
    * use mock inject function to inject `$componentController` service.
* In the test method:
    * set up a bindings object with expected props (if any);
    * set up objects controller expects to be injected (if any);
    * create controller with `$componentController('componentName', injections, bindings)`.
***