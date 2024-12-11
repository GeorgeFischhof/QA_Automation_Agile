Test framework should 
- be "IDE friendly": for example should create classes, models, so the IDE can help with auto-completion. (I use Pydantic models for this purpose)
- contain small (low level) and bigger (high level) helpers to enable granular setting if needed
- contain helpers that are able to execute negative test cases (some stuff can only be used in the good way, wrong data can not be sent through, but negative test cases need wrong data)
- be able to use tagging, to be able to select which tests to execute in a given run. 
  Tags can be relate to: test type (smoke, sanity, regression ...), execution time (slow), execution place (UI, API, local, CI), function ... (I use PyTest; it has very good tagging possibilities)
