This file holds the tests that you create. Remember to import the python file(s)
you wish to test, along with any other modules you may need.
Run your tests with "python3 ok -t --suite SUITE_NAME --case CASE_NAME -v"
--------------------------------------------------------------------------------

Suite 1

	>>> from ants import *

	Case Example
		>>> x = 5
		>>> x
		5


Suite 2

		Case 1

				>>> import ants, importlib
				>>> importlib.reload(ants)
				>>> hive = ants.Hive(ants.AssaultPlan())
				>>> dimensions = (2, 9)
				>>> colony = ants.AntColony(None, hive, ants.ant_types(),
				...         ants.dry_layout, dimensions)
				>>> ants.bees_win = lambda: None
				>>> # QueenAnt Placement
				>>> queen = ants.QueenAnt()
				>>> impostor = ants.QueenAnt()
				>>> front_ant, back_ant = ants.ThrowerAnt(), ants.ThrowerAnt()
				>>> tunnel = [colony.places['tunnel_0_{0}'.format(i)]
				...         for i in range(9)]
				>>> tunnel[1].add_insect(back_ant)
				>>> tunnel[7].add_insect(front_ant)
				>>> tunnel[4].add_insect(impostor)
				>>> queen.action(colony)
				>>> print(places_before_queen)
