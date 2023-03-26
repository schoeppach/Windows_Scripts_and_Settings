## USB schreibschutz aufheben formatieren

### [Windows] + [R]
	diskpart

### laufwerke anzeigen
	list disk

### laufwerk auswaehlen
	select disk X

### schreibschutz entfernen
	attributes disk clear readonly
	
### laufwerk bereinigen
	clean
	

### formatieren partitionieren
	create partition primary
	select partition 1
	format fs=FAT32 quick
	active
