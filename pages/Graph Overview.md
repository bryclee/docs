- #+BEGIN_NOTE
  This page describes how this graph and its pages are organized. This is meant to be read by those looking for ways to manage their graph and does not serve as a guide for first time users.
  #+END_NOTE
- ## Class Hierarchy
  *Note:* This section shows how classes or types of pages are related to each other. A class groups pages that share a common set of properties. `Thing` is the root class from which all other classes are defined. When a class is a child of another class, it usually inherits using the same properties as its parent class.
	- [[Thing]]
		- [[Class]]
		- [[FeatureTag]]
		- [[Feature]]
			- [[Command]]
			- [[Whiteboard/Tool]]
		- [[Platform]]
		- [[Property]]
		- [[UI Element]]
			- [[Whiteboard/Object]]
- ## Pages by Class
  *Note:* This section shows the types of pages or "things" that are available in this graph. Click on a class page and look under its pages query to see its corresponding pages. For example, expand `Feature pages` query to reveal the 50+ feature pages.
	- [[Thing]]
		- [[Class]]
		  collapsed:: true
			- collapsed:: true
			  #+BEGIN_QUERY
			  {:query (page-property :type [[Class]])
			  :title "Class pages"}
			  #+END_QUERY
		- [[FeatureTag]]
		  collapsed:: true
			- query-table:: true
			  collapsed:: true
			  #+BEGIN_QUERY
			  {:query (page-property :type [[FeatureTag]])
			  :title "FeatureTag pages"}
			  #+END_QUERY
		- [[Feature]]
			- query-table:: true
			  query-properties:: [:page :type :platforms :description :initial-version :tags]
			  collapsed:: true
			  #+BEGIN_QUERY
			  {:query (page-property :type [[Feature]])
			  :title "Feature pages"}
			  #+END_QUERY
			- [[Command]]
			  collapsed:: true
				- query-sort-by:: page
				  query-table:: true
				  query-sort-desc:: false
				  query-properties:: [:name :page :description]
				  #+BEGIN_QUERY
				  {:query (property :type [[Command]])
				  :result-transform (fn [res] (map (fn [m] (assoc-in m [:block/properties :name] (get-in m [:block/page :block/original-name]))) res))
				  :title "Commands"}
				  #+END_QUERY
				- query-table:: true
				  #+BEGIN_QUERY
				  {:query (property :type [[Command]])
				  :title "Commands"}
				  #+END_QUERY
			- [[Whiteboard/Tool]]
			  collapsed:: true
				- collapsed:: true
				  #+BEGIN_QUERY
				  {:query (page-property :type [[Tool]] )
				  :title "Whiteboard/Tool pages"}
				  #+END_QUERY
		- [[Platform]]
		  collapsed:: true
			- collapsed:: true
			  #+BEGIN_QUERY
			  {:query (page-property :type [[Platform]] )
			  :title "Platform pages"}
			  #+END_QUERY
		- [[Property]]
		  collapsed:: true
			- collapsed:: true
			  #+BEGIN_QUERY
			  {:query (page-property :type [[Property]])
			  :title "Property pages"}
			  #+END_QUERY
		- [[UI Element]]
			- collapsed:: true
			  #+BEGIN_QUERY
			  {:query (page-property :type [[UI Element]] )
			  :title "UI Element pages"}
			  #+END_QUERY
			- [[Whiteboard/Object]]
			  collapsed:: true
				- collapsed:: true
				  #+BEGIN_QUERY
				  {:query (page-property :type [[Whiteboard/Object]] )
				  :title "Whiteboard/Object pages"}
				  #+END_QUERY