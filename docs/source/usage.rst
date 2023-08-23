Usage
=====

Installation
------------

To use simplistic, first install it using pip:

.. code-block:: console

   (.venv) $ pip install simplistic

Example
------------
Wrapping a CLI command using simplistic is simple:

.. code-block:: console

	class CLI(Trait):
	
		_target_dict = {'all': '--all'}
		_option_dict = {'json': '--json'}
		
		def clean():
			self._command_seq = ['conda','clean']
			
			return self
	
	
	cli = CLI
	cmd, stdout = cli.clean().target("all").options("json")
	print(cmd)
	>>['conda','clean','--all','--json']