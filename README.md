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