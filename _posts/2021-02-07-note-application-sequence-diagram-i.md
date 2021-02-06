---
title: Note Application - Sequence Diagram-I
layout: post
tags:
- noteapplication
- sequencediagram
comments: true
---

Hi all,

We will talk about sequence diagram of note application in the previous post.  Sequence diagrams is referred flow of process. We apply this approach for the note application.
Firstly drew  for "show all notes" use case.

"Show all notes" sequence diagram:
![]({{ 'assets/img/noteapp_sequence_diagram.png' | relative_url }})


"NoteListFragment" class extends from "Fragment" abstract class.  "getNotesByLimit" method of "NoteDatabase" extended from "RoomDatabase" is called inside "onViewCreated" method of "NoteListFragment".

In this step we can write code template on based the sequence diagram.

<ins>NoteFragment.java</ins>
{% highlight java  linenos %}
public class NoteFragment extends Fragment {
	public void onViewCreated(@NonNull View view, Bundle savedInstanceState) {
		..
		NoteDatabase noteDatabase = NoteDatabase.getDatabase(view.getContext());
		NoteDao noteDao =  noteDatabase.noteDao();
		List<Note> notes =  noteDao.getByLimit(limit, offset);
		..
	}
}
{% endhighlight %}
	
	
	
<ins>NoteDatabase.java</ins>
{% highlight java  linenos %}
@Database(entities = {Note.class}, version = 1)
public abstract class NoteDatabase extends RoomDatabase {
    private static volatile NoteDatabase INSTANCE;

    static NoteDatabase getDatabase(final Context context) {
        if (INSTANCE == null) {
            synchronized (NoteDatabase.class) {
                if (INSTANCE == null) {
                    INSTANCE = Room.databaseBuilder(context.getApplicationContext(),
                            NoteDatabase.class, "note_database")
                            .build();
                }
            }
        }
        return INSTANCE;
    }


    public abstract NoteDao noteDao();
}
{% endhighlight %}
	
	
	
<ins>NoteDao.java</ins>
{% highlight java  linenos %}
@Dao
public interface NoteDao {
    @Query("SELECT * FROM notes LIMIT :limit OFFSET :offset")
    List<Note> getByLimit(int limit, int offset);

}

{% endhighlight %}
	
	
	
<ins>NoteDao.java</ins>
{% highlight java  linenos %}
@Entity
public class Note {
	..
}
{% endhighlight %}

	
We designed sequence diagram and wrote class on based this sequence diagram. Next article we're going to design class diagram of use case that we selected as "show all notes".
