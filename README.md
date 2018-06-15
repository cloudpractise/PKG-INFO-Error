# Fix the issue of python PKG-INFO error
Fix the issue of "Python PIP KeyError with No metadata except PKG-INFO is available"

At MAC OSX 10.12.6/Python 2.7.10/PIP 10.0.1, when using "pip any_package.py install" and/or "pip install any_package", the terminal CLI says:
-------- 
Exception:
Traceback (most recent call last):
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_internal/basecommand.py", line 228, in main
    status = self.run(options, args)
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_internal/commands/install.py", line 318, in run
    self._warn_about_conflicts(to_install)
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_internal/commands/install.py", line 442, in _warn_about_conflicts
    package_set, _dep_info = check_install_conflicts(to_install)
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_internal/operations/check.py", line 89, in check_install_conflicts
    state = create_package_set_from_installed()
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_internal/operations/check.py", line 39, in create_package_set_from_installed
    retval[name] = PackageDetails(dist.version, dist.requires())
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_vendor/pkg_resources/__init__.py", line 2613, in requires
    dm = self._dep_map
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_vendor/pkg_resources/__init__.py", line 2864, in _dep_map
    self.__dep_map = self._compute_dependencies()
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_vendor/pkg_resources/__init__.py", line 2873, in _compute_dependencies
    for req in self._parsed_pkg_info.get_all('Requires-Dist') or []:
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_vendor/pkg_resources/__init__.py", line 2855, in _parsed_pkg_info
    metadata = self.get_metadata(self.PKG_INFO)
  File "/Library/Python/2.7/site-packages/pip-10.0.1-py2.7.egg/pip/_vendor/pkg_resources/__init__.py", line 1794, in get_metadata
    raise KeyError("No metadata except PKG-INFO is available")
KeyError: 'No metadata except PKG-INFO is available  
----- 
To fix the issue, just simplly type the following command in the MAC CLI termical: 
$ brew install python2 --framework --universal
$ pip install --upgrade pip setuptools

Then everything is ok and have fun!
