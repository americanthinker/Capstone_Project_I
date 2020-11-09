# The Story of the Special Operations Veteran community: In Transition  
  
  
<p align="center">
  <img align="center" src="/images/NavySEALs.png" width="600" title="Navy SEALs">
</p>  
  
  
# Setting the Stage: Background Part I
The US Special Operations community is a diverse group of highly trained men and women dedicated to the cause of ["protecting and advancing U.S. policies and objectives across the international arena"](https://www.socom.mil/about).   The community is composed of Special Operations Forces (SOF) "tribes" from all branches of the Department of Defense to include the Navy SEALs, Army Green Berets, Air Force Pararesucmen, and Marine Raiders, among other specialized units.  This highly talented subset of the overall US population, at some point in their military career, makes the decision to "put down their ruck sack", "hang up their uniform" and transition into civlian life. 

<p align="center">
  <img align="center" src="/images/mil-civ.png" width="200" height="250" title="Mil to Civ">
</p>

As a former SEAL turned Data Scientist I partnered with [Elite Meet](https://elitemeetus.org/) - a 501(c)(3) non-profit Veteran Service Organization dedicated to providing a post-military SOF network and connecting its members to leaders in the Corporate sector - to conduct an analysis on this group of veterans to paint a holistic picture of who they are and where they are headed.  This analysis answers the following questions:
- Where does this post-military network live?
- What is the composition (by tribe) of the overall community?
- What are the descriptive charateristics of this group: Age, Education, XXX
- How prepared is this group for the Corporate workforce?
- What is the growth over time

# The Data
I was granted access to an anonymized section of the Elite Meet (EM) membership database which consisted of 750+ entries of SOF veteran members.  This initial dataset was curated from the EM Salesforce instance, which in turn was collected from individual membership intake forms at time of EM application.  Because many of the intake form fields were free form, the dataset required an extensive amount of cleaning in order to conduct an accurate analysis.  As an example, something as simple as inputting a "Current Location" oftentimes included several variations, as shown in the figure below: 
<p align="center">
  <img align="center" src="/images/Excel_cleaned.png" width="500" title="Data cleaning">
</p>
The dataset originally contained more than 50 features/columns, but after reviewing the data I was able to reduce the number of features to 34.  Here's a quick look at what the set looks like:

# Geographic Distribution

**Challenge:** One of the first things that the CEO of Elite Meet wanted to know is how are the members geographically distributed?  One of the original ideas behind the Elite Meet brand was to establish regional chapters that would serve to support members in the local area.  The CEO wanted to get a good sense of where it made sense to push for regional chapters.  
**Solution:** I decided that a heat map, which displays the denisty of points on a map represented by color intensity (heat), would be a good way of visualizing the membership geogrpahic distribution.  I originally decided to work with Folium, which is a Python library with a Javascript backend that provides mutiple dynamic, interactive overlays.  However, after working with the library I realized that the weights function was not working which is a known issue with the library.  I ended up working with the Google Maps API, which required creating an account to get an API Key.  Below is the final result:

<p align="center">
  <img align="center" src="/images/National.png" width="1000" title="National Distribution">
</p>  
                                                                               
Anyone familiar with the SOF community would not be surprised by this distribution.  Members are clustered around all of the major military bases housing SOF personnel - 1st Special Forces Group in Seattle, Navy SEALs and Navy pilots in San Diego and Virgina Beach, 5th Special Forces Group in Kentucky, 3rd Special Forces Group in North Carolina as well as the Raiders out of Camp Lejune, and the list goes on.  To get a better sense of the distributions on the coasts where the majority of members are concentrated I provided the following zoomed-in images:

<p float="left">
  <img src="/images/WC.png" width="450" title="West Coast distribution"/>
  <img src="/images/EC.png" width="450" title="East Coast distribution"/> 
</p>
                                                                               
## Community Breakdown by Tribe
<p align="center">
  <img align="center" src="/images/SOF-Breakdown.png" width="1000" title="SOF Tribes">
</p>
