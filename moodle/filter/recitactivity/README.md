# mp-filter-recitautolink

## Credits 

This plugin is a fork from git@github.com:SN-RECIT-formation-a-distance/moodle-filter_recitautolink.git. And then a bunch of stuffs are modified and added. They branch off extremely and being renamed to a different plugin. 

To pull from the original, use the following command

```sh 
git pull original-origin master
```

You can see the remote repo using 

```sh
git remote -v 
# origin  git@github.com:HananoshikaYomaru/moodle-filter_shortcode.git (fetch)
# origin  git@github.com:HananoshikaYomaru/moodle-filter_shortcode.git (push)
# original-origin git@github.com:SN-RECIT-formation-a-distance/moodle-filter_recitautolink.git (fetch)
# original-origin git@github.com:SN-RECIT-formation-a-distance/moodle-filter_recitautolink.git (push)
```

## Introduction

This filter allows, among other things, the display of the activity icon as well as a check mark indicating the status of a completed activity. It also allows you to take advantage of Moodle's database and create a more personalized experience. The examples below show you the available integration codes and the result on the user's screen.

[![Youtube video](https://img.youtube.com/vi/FkpwLCFOUTU/0.jpg)](https://www.youtube.com/watch?v=FkpwLCFOUTU)

## Generation of the student's avatar or name
<img src='https://github.com/SN-RECIT-formation-a-distance/moodle-filter_recitautolink/blob/master/docs/filtre1.jpg' alt="Generation of the student's avatar or name" style='width: 500px;'/>
The attached example shows the display of the student's name on a page. The left side shows the learner's screen. On the right side, we see the embedding code in the editor. The `[[d/user.firstname]]` parameter causes the student's first name to be displayed. The information is taken from the database.

# Technical information
Represents the separator character used in the filter. If the character is <b>/</b>, the filter will search for it in <b>[[i/activityname]]</b>. All indicators ( i/, c/, d/ ) must be at the begenning of double brackets [[.<br/>

## Integration Code
- **[[activityname]]**: Activity name link.
- **[[i/activityname]]**: Activity name link with icon.
- **[[c/activityname]]**: Activity name link with completion checkbox.
- **[[i/c/activityname]]**: Activity name link with icon and completion checkbox.
- **[[/i/c/desc:"Name"/]]** activityname: Change link name.
- **[[/i/c/class:"btn btn-primary"/]]**: Add CSS classes.
- **[[c/b/activityname]]** or **[[i/c/b/activityname]]**: Open the link to an activity in another tab.
- **[[s/sectionname]]** or **[[s/6]]**: Link to a section (e.g., section 6 if its name is not personalized; not usable in edit mode).
- **[[d/course.fullname]]**, **[[d/course.shortname]]**: Course information.
- **[[d/user.firstname]]**, **[[d/user.lastname]]**, **[[d/user.email]]**, **[[d/user.picture]]**: Student's first name, last name, email, and avatar.
- **[[d/teacher1.firstname]]**, **[[d/teacher1.lastname]]**, **[[d/teacher1.email]]**, **[[d/teacher1.picture]]**: First teacher's first name, last name, email, and avatar. The teacher must be in the group for their name to appear. Same for teacher2, teacher3, etc., for all teachers for that course.
- **[[h5p/Name of H5P]]**: Link to H5P content.

## How to install? 

Just zip this folder and install by `.zip`. 


## How to start development ? 

1. Spin up your docker Moodle container, I recommend using bitnami moodle. 
2. navigate to `filter`
3. git clone this repo, the folder name must be `recitactivity`
4. run `php admin/cli/upgrade.php --non-interactive`. There you go 🚀. 


## Testing

This is a filter plugin. The best way to test it is to find a HTML input and write a list of test shortcodes to test it. You can use the tiny_shortcode plugin to do this.
