geo_atom.py
===========

GeoRSS version of the AtomFeed from werkzeug.contrib.atom. Only does Recognizes Point. 

Ex.
      feed = GeoAtomFeed(job.name, feed_url=request.url, url=request.url_root )
    articles = get_data(job_slug, time)
    for article in articles:
        if len(article['coordinate_string']) > 0:
            lat_lon = [str(article['coordinates']['lat']), str(article['coordinates']['lon'])]
        else:
            lat_lon = None

        feed.add(article["title"], unicode(article['data']),
            content_type='html',
            author=article['author'],
            id=article['id'],
            url=article['url'],
            updated=article['updated'],
            published=article['published'],
            lat_lon=lat_lon)
