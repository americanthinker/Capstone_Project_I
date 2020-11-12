# The Story of the Special Operations Veteran community: In Transition  
  
  
<p align="center">
  <img align="center" src="/images/NavySEALs.png" width="600" title="Navy SEALs">
</p>  
  
  
# Setting the Stage: Background 
The US Special Operations community is a diverse group of highly trained men and women dedicated to the cause of ["protecting and advancing U.S. policies and objectives across the international arena"](https://www.socom.mil/about).   The community is composed of Special Operations Forces (SOF) "tribes" from all branches of the Department of Defense to include the Navy SEALs, Army Green Berets, Air Force Pararesucmen, Marine Raiders, and jet and helo pilots, among other specialized units.  This highly talented subset of the overall US population, at some point in their military career, makes the decision to "put down their ruck sack", "hang up their uniform" and transition into civlian life. 

<p align="center">
  <img align="center" src="/images/mil-civ.png" width="200" height="250" title="Mil to Civ">
</p>

As a former SEAL turned Data Scientist I partnered with [Elite Meet](https://elitemeetus.org/) - a 501(c)(3) non-profit Veteran Service Organization dedicated to providing a post-military SOF network and connecting its members to leaders in the Corporate sector - to conduct an analysis on this specialized group of veterans to paint a holistic picture of who they are and where they are headed.  This analysis addresses the following questions:
- Where does this post-military network live?
- What is the composition (by tribe) of the overall community?
- What are the descriptive charateristics of this group: age, education, years of experience,...
- How prepared is this group for the Corporate workforce?
- How has Elite Meet grown over time and through what channels?

# The Data
I was granted access to an anonymized section of the Elite Meet (EM) membership database which consisted of 750+ entries of SOF veteran members.  This initial dataset was curated from the EM Salesforce instance, which in turn was collected from individual membership intake forms at time of EM application.  Because many of the intake form fields were free form, the dataset required an extensive amount of cleaning in order to conduct an accurate analysis.  As an example, something as simple as inputting a "Current Location" oftentimes included several variations, as shown in the figure below: 
<p align="center">
  <img align="center" src="/images/Excel_cleaned.png" width="500" title="Data cleaning">
</p>
The dataset originally contained more than 50 features/columns, but after reviewing the data I was able to reduce the number of features to 34.  Here's a quick look at what the set looks like:

# Geographic Distribution

#### <ins>Challenge</ins>  
One of the first things that the CEO of Elite Meet wanted to know is how are the members geographically distributed?  One of the original ideas behind the Elite Meet brand was to establish regional chapters that would serve to support members in the local area.  The CEO wanted to get a good sense of where to make a marketing push for regional chapters.  

#### <ins>Solution</ins>  
I decided that a heat map, which displays the denisty of points on a map represented by color intensity (heat), would be a good way of visualizing the membership geogrpahic distribution.  I originally decided to work with Folium, which is a Python library with a Javascript backend that provides mutiple dynamic, interactive overlays.  However, after working with the library I realized that the weights function was not working which is a known issue with the library.  I ended up working with the Google Maps API, which required creating an account to get an API Key.  Below is the final result:

<p align="center">
  <img align="center" src="/images/National.png" width="1000" title="National Distribution">
</p>  
                                                                               
Anyone familiar with the SOF community would not be surprised by this distribution.  Members are clustered around all of the major military bases housing SOF personnel - 1st Special Forces Group in Seattle, Navy SEALs and Navy pilots in San Diego and Virgina Beach, 5th Special Forces Group in Kentucky, 3rd Special Forces Group in North Carolina as well as the Raiders out of Camp Lejune, and the list goes on.  To get a better sense of the East Coast distribution, which is a little busier than the West Coast map, I provided the following zoomed-in image:

<p align="center">
  <img align="center" src="/images/EC.png" width="800" title="EC Distribution">
</p>  
Admittedly, I do poke a little fun here at the East Coast distribution.  While it's obvious to someone familiar with SOF bases that the large clusters in the Virginia Beach area are SEALs and Navy pilots, the clusters in the Fayettville and Raleigh area are Green Berets, and the Wilmington and Jacksonville, NC clusters are Marine Raiders, it takes an Elite Meet insider to know that the cluster in the DC area is guys retiring out of the Pentagon or looking to work in the Fed Gov space and that the cluster in New York City is the Private Equity and Investment Banking crowd, which is and always has been a favorite industry of choice for SOF veterans.  
&nbsp;  

* For an interactive solution to visualizing the national distribution of EM members click on the link below:  
[National Distribution](https://americanthinker.github.io/em_map.github.io/)  

# Community Makeup (by Tribe)  

#### <ins>Challenge</ins>  
Next on the list was providing the CEO with an understanding of the actual makeup of the Elite Meet community, specifically by SOF "Tribe".  There are many different SOF variants and members were given free reign to describe their primary job duties at the time of application and therefore exact tribal classification was not readily apparent to the casual observer.  A better understanding of the community makeup allows the CEO to ensure that outreach efforts are balanced across the Defense service branches and that she can communicate an accurate picture of the community to potential hiring partners/managers.  

#### <ins>Solution</ins>  
I provided two diagrams:
1. First chart provides the SOF Tribe breakout by service (Navy, Army, Air Force, Marine Corps)
2. Second chart provides a holistic overview of the entire community at once  
  
For those unfamilar with the several SOF variants that make up US Special Forces, some of the acronyms in the below charts might not make any sense, so I've created a brief non-exhaustive glossary below.  Also, for standardization across graphics the following color chart will is used in keeping with traditional military coloring of the service branches:  
- Army = Green 
- Navy = Blue
- Air Force = Sky Blue
- Marine Corps = Red
- Joint = Purple (mix of branches)  
<H1 align="center" style="font-family:georgia;"> SOF Glossary</H1>
<p align="center">
  <img align="center" src="/images/Glossary.png" width="800" title="Glossary">
</p>   
<p></p>  

This first chart breaks out the community by tribe within their respective service branches.  For example, 46.7% of all SOF Navy personnel are SEALs while 13.7% are SWCC.  No real suprises here with regard to the community makeup.  
<p></p>
<p align="center">
  <img align="center" src="/images/Tribes_by_Service.png" height="600" width="1000" title="Holistics Overview">
</p>  
  
This second chart provides both a side-by-side bar chart comparison of raw counts, as well as a "Tree Map" which shows proportionality in a different visual style.  Two points to note here.  
- Given the size of the Army Special Forces, one should expect about a 3:1 ratio of Army to Navy personnel in these charts.  But, given that Elite Meet was originally founded by a Navy SEAL and SWCC member, much of the initial community was comprised of Navy personnel given the word-of-mouth nature of recruitement.  As you'll see in one of the following charts, Army personnel do start to pick up their numbers in more recent months, but even still, they are vastly underrepresented in the Elite Meet community given their associated active duty population size.  
- Second point to note is that about 20% (1 in 5 members) of the community are fighter and helo pilots, which is far more than I would have originally assumed.  I'm not sure what the total numbers are for the pilot communities within the Department of Defense, so perhaps 20% is right where they should be, but either way their healthy membership numbers indicates that the word is out within the pilot community that Elite Meet is a good network to be a part of.  

<p align="center">
  <img align="center" src="/images/SOF_Tribes.png" width="1000" title="SOF Tribes">
</p>  
  
# Individual Stats   

#### <ins>Challenge</ins>
It's now time to turn to the individuals that make up this community.  The CEO wanted to know some basic statistics on the following:  
- Years of Experience 
- Education Levels 
- Target Industries

#### <ins>Solution</ins>  
The following graphs/charts begin to paint a picture of what a veteran from this community looks like, with some interesting suprises along the way.

#### Years of Experience  
To begin, we start with a distribution of the years of experience found within the community.
<p align="center">
  <img align="center" src="/images/Years_Experience.png" width="1000" title="Years of Exp">
</p>  
We can clearly see that this distribution is bimodal, with the peaks located at the 10-year and 20-year marks, and a valley between 12 - 18 years.  This bimodal distribution is explained by the 20-year requirement for Active Duty military retirement.  For most in the military, the 10-year mark is an inflection point, where one must make the decision to break with the military and pursue a civilian career or stick it out for the full 20 as a "lifer".   This inflection point is visually displayed in the chart below:  
<p align="center">
  <img align="center" src="/images/YearsExperience_Bucket.png" width="400" title="Years of Exp Bucket">
</p>  
The key takeaway here for the Elite Meet CEO is that she is working with two distinct sub-groups within the overall population, each with different needs.  The "less than 12 year" crowd is going to have different salary requirements and runway than will the crowd with 17+ years of experience.  Decisions around resourcing and offerings should take the needs of these groups into account.   

#### Education Levels  
So how educated (formally) are the veterans from the Elite Meet community?  Surprisingly enough (to me) - very. 
<p align="center">
  <img align="center" src="/images/Education_Levels.png" width="1000" title="Education">
</p> 

<table>
<tr><th>% of Undergrad Degrees: By Branch </th><th>% of Grad Degrees: By Branch</th></tr>
<tr><td>

|Branch| Percent |
|------|---------|
| Marine Corps|82.0%  |
| Air Force|80.3% |
| Army|71.0%  |
| Navy|69.5% |

</td><td>

|Branch| Percent |
|------|---------|
| Air Force|43.9%  |
| Marine Corps|36.1% |
| Army|28.1%  |
| Navy|26.5% |

</td></tr> </table>
