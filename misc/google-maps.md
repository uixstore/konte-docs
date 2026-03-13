# Google Map API Key


Google Map requires an API key if you want to display a map on your website. To get an API key, you can follow this documentation:

[Create API keys](https://developers.google.com/maps/documentation/javascript/get-api-key)

There are some problem people usually made when creating a Google Map API key and they causes the map not working.

1. Forgot to setup the billing information: Even with the free usage, Google requires you to fill the billing information. Without this information, your API key won't work.

1. Setup the wrong restriction for the API key: You should ensure the following API are enabled along with your API key.

	- Google Maps Javascript API
	- Google Maps Geocoding API
	- Google Places API
	- Google Maps Directions API

1. They map still saying the API key is not usable: Google Maps has some limitation with the free usage. Therefore the API key can't get the coordinates from the address you entered for the map. Basisly, we strongly recommend users to use the optio for latitude and longitude instead of the option map address.

You can get the coordinates right on the google map website/app. Please follow this documentation to get them.

[Find the coordinates of a place](https://support.google.com/maps/answer/18539?co=GENIE.Platform%3DDesktop&hl=en)

Or you can use a free service which provide a more friendly interface to get the coordinates from your address. For example you can use this website:

- https://www.latlong.net/

- https://www.gps-coordinates.net/