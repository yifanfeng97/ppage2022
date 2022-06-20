<template>
  <v-container>
    <v-row class="text-center">
      <p class="text-h4">Released Datasets</p>
    </v-row>
    <v-row>
      <v-col cols="12" class="text-h6">OS-MN40 and OS-MN40-Miss</v-col>
      <v-col cols="12" class="text-body-1">
        <p>
          We released two datasets in SHREC'22 Track:
          <a
            class="text-decoration-none"
            href="https://www.moon-lab.tech/shrec22"
            target="_blank"
            >Open-Set 3D Object Retrieval</a
          >. The objective of this track is to evaluate the performance of the
          different 3D shape retrieval algorithms under the Open-Set setting,
          which is an unknown-category shape retrieval task (each object
          contains multi-modal and multi-resolution representations: mesh, point
          cloud, voxel, and multi-view). In this setting, the retrieval and
          representation models are trained using known-category 3D objects and
          unknown-category 3D data are used for retrieval. This track includes
          two datasets, OS-MN40 and OS-MN40-Miss. Each object in OS-MN40 has
          complete four types of modalities and each object in OS-MN40-Miss
          contains incomplete data. Note that the two datasets are generated
          based on
          <a
            class="text-decoration-none"
            href="https://modelnet.cs.princeton.edu/"
            target="_blank"
            >ModelNet40</a
          >. More details can be found
          <a
            class="text-decoration-none"
            href="https://www.moon-lab.tech/shrec22"
            target="_blank"
            >here</a
          >.
        </p>
        <p>
          <strong>OS-MN40:</strong> An Open-Set 3D object retrieval dataset.
          Each 3D object in this dataset is represented with multi-modality and
          multi-resolution (1024 points and 2048 points for point cloud, 32
          times 32 times 32 resolution and 64 times 64 times 64 resolution for
          voxel, 24 views captured with 15 horizon interval cameras for
          multi-view and raw number face and simplified 500 faces for Mesh).
          Most objects in OS-MN40 are selected from the ModelNet40 dataset.
          OS-MN40 consists of 12309 objects from 40 classes. For each object, we
          provide four modalities (Point cloud, Voxel, Multi-view, and Mesh).
          Note that the dataset is collected for an open-set 3D retrieval
          setting. Thus, the categories in training and retrieval are not
          shared. Eight classes, including airplane, flower pot, glass box,
          keyboard, monitor, night stand, sink, and table, are selected for
          training. Other 32 classes, like bed, chair, plant, bathtub, and cup,
          are selected for retrieval, which are unknow-category in the training
          stage.
        </p>
        <p>
          <strong>OS-MN-40-Miss: </strong> This sub-dataset is constructed by
          random drop arbitrary modality with probability 0.4 for each object.
          OS-MN40-Miss is collected towards modality missing problem.
        </p>
        <p>
          <strong>Downloads: </strong>
          <a
            class="text-decoration-none"
            href="https://data.shrec22.moon-lab.tech:18443/SHREC22/OS-MN40.tar.gz"
            target="_blank"
          >
            OS-MN40(~46G)</a
          >,
          <a
            class="text-decoration-none"
            href="https://data.shrec22.moon-lab.tech:18443/SHREC22/OS-MN40-Miss.tar.gz"
            target="_blank"
            >OS-MN40-Miss(~28G)</a
          >,
          <a
            class="text-decoration-none"
            href="https://github.com/yifanfeng97/OS-MN40-Example"
            target="_blank"
            >Example Code</a
          >.
        </p>
      </v-col>
      <v-col cols="12" class="d-flex justify-center">
        <v-img
          src="publication/2022-shrec22/fw.png"
          max-height="300"
          contain
        ></v-img>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" class="text-h6"
        >OS-ESB-core, OS-NTU-core and OS-MN40-core</v-col
      >
      <v-col cols="12" class="text-body-1">
        <p>Coming Soon...</p>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "MyDataset",

  data: () => ({}),
};
</script>
