sync/stylindex:
	rsync -ua stylindex/stylindex-web-gitlab/ ../stylindex/stylindex-web/ --delete --exclude-from 'exclude.txt'

r-sync/stylindex:
	rsync -ua ../stylindex/stylindex-web/ stylindex/stylindex-web-gitlab/ --delete --exclude-from 'exclude.txt'

sync/visionarea:
	rsync -ua visionarea/visionarea-front-gitlab/ ../visionarea-front/ --delete --exclude-from 'exclude.txt'

r-sync/visionarea:
	rsync -ua ../visionarea-front/ visionarea/visionarea-front-gitlab/ --delete --exclude-from 'exclude.txt'

.PHONY: sync/stylindex